---
title: 'CA2117: APTCA-Typen sollten nur APTCA-Basistypen erweitern | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2117
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
helpviewer_keywords:
- AptcaTypesShouldOnlyExtendAptcaBaseTypes
- CA2117
ms.assetid: c505b586-2f1e-47cb-98ee-a5afcbeda70f
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: be208c156e8710b6aa6b2821a5a85131f3c2e4b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ca2117-aptca-types-should-only-extend-aptca-base-types"></a>CA2117: APTCA-Typen sollten nur APTCA-Basistypen erweitern
|||  
|-|-|  
|TypeName|AptcaTypesShouldOnlyExtendAptcaBaseTypes|  
|CheckId|CA2117|  
|Kategorie|Microsoft.Security|  
|Unterbrechende Änderung|Breaking|  
  
## <a name="cause"></a>Ursache  
 Ein öffentlicher oder geschützter Typ in einer Assembly mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> -Attribut erbt von einem Typ in einer Assembly, die das Attribut nicht deklariert.  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Standardmäßig werden öffentliche oder geschützte Typen in Assemblys mit starken Namen implizit durch geschützt ein <xref:System.Security.Permissions.SecurityAction.InheritanceDemand> für volle Vertrauenswürdigkeit. Assemblys mit starken Namen gekennzeichnet, mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA) verfügen nicht über diesen Schutz. Das Attribut wird die vererbungsanforderung deaktiviert. Auf diese Weise verfügbar gemachte deklarierte Typen in der Assembly vererbbar von Typen, die keine volle Vertrauenswürdigkeit haben.  
  
 Wenn das APTCA-Attribut in einer voll vertrauenswürdigen Assembly vorhanden ist, und eine in der Assembly von einem Typ erbt, der keine teilweise vertrauenswürdigen Aufrufer zulässt, kann diese Sicherheitslücke ausgenutzt. Wenn zwei Typen `T1` und `T2` die folgenden Bedingungen erfüllen, können böswillige Aufrufer mithilfe des Typs `T1` die vererbungsanforderung implizite volle Vertrauenswürdigkeit umgangen werden, die schützt `T2`:  
  
-   `T1`in einer voll vertrauenswürdigen Assembly, die über das APTCA-Attribut verfügt, wird ein öffentlicher Typ deklariert werden.  
  
-   `T1`von einem Typ erbt `T2` außerhalb der Assembly.  
  
-   `T2`die Assembly verfügt nicht über das APTCA-Attribut und aus diesem Grund sollten nicht von den Typen im teilweise vertrauenswürdigen Assemblys geerbt werden.  
  
 Eine teilweise vertrauenswürdige Typ `X` erben können `T1`, ermöglicht er Zugriff auf geerbte Member deklariert `T2`. Da `T2` verfügt nicht über das APTCA-Attribut, dessen sofortige abgeleiteten Typ (`T1`) erfüllen muss eine vererbungsanforderung voll vertrauenswürdig sind. `T1` ist voll vertrauenswürdig und erfüllt daher diese Überprüfung. Das Sicherheitsrisiko, da `X` nicht beteiligt, erfüllen die vererbungsanforderung, die schützt `T2` aus nicht vertrauenswürdigen-Unterklasse. Aus diesem Grund müssen Typen mit dem APTCA-Attribut nicht Clienttypen erweitern, die nicht mit das Attribut verfügen.  
  
 Eine andere Sicherheitsproblem und einem häufiger ist, die den abgeleiteten Typ (`T1`), durch den Programmierer-Fehler verfügbar machen geschützte Member des Typs, die volle Vertrauenswürdigkeit erforderlich sind (`T2`). In diesem Fall erhalten nicht vertrauenswürdige Aufrufern Zugriff auf Informationen, die nur für voll vertrauenswürdige Typen verfügbar sein sollen.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Wenn der Typ durch den Verstoß gemeldet in einer Assembly, die nicht über das APTCA-Attribut erforderlich ist, entfernen Sie sie.  
  
 Wenn das APTCA-Attribut erforderlich ist, fügen Sie in den Typ einer vererbungsanforderung für volle Vertrauenswürdigkeit. Dies schützt vor Vererbung von nicht vertrauenswürdigen Typen.  
  
 Es ist möglich, einen Verstoß zu beheben, durch das APTCA-Attribut hinzufügen, auf die Assemblys der Basistypen, die durch den Verstoß gemeldet. Tun Sie dies ohne Durchführen von einer rechenintensiven sicherheitsreview der gesamte Code in den Assemblys und der gesamte Code, der auf die Assemblys abhängig ist.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Um eine Warnung dieser Regel sicher zu unterdrücken, müssen Sie sicherstellen, dass geschützte Member, die von Ihrem Typ verfügbar gemacht werden keine direkt oder indirekt dürfen nicht vertrauenswürdige Aufrufern Zugriff auf vertrauliche Informationen, Vorgänge oder Ressourcen, die einen destruktiven Weise verwendet werden können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird zwei Assemblys und eine testanwendung, um die von dieser Regel erkannte Sicherheitslücke zu veranschaulichen. Die erste Assembly verfügt nicht über das APTCA-Attribut sollte auch nicht von teilweise vertrauenswürdigen Typen geerbt (dargestellt durch `T2` im vorherigen Beispiel).  
  
 [!code-csharp[FxCop.Security.NoAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Die zweite Assembly, dargestellt durch `T1` aus dem vorherigen Beispiel ist vollständig vertrauenswürdig und lässt teilweise vertrauenswürdige Aufrufer.  
  
 [!code-csharp[FxCop.Security.YesAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Testtyp, dargestellt durch `X` aus dem vorherigen Beispiel ist in einer teilweise vertrauenswürdigen Assembly.  
  
 [!code-csharp[FxCop.Security.TestAptcaInherit#1](../code-quality/codesnippet/CSharp/ca2117-aptca-types-should-only-extend-aptca-base-types_3.cs)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
 **Treffen am abgewandte Glen 2/22/2003 12:00:00 Uhr!**  
**Sonnig umgewandelte aus Test:**  
**Treffen am sonnig umgewandelte 2/22/2003 12:00:00 Uhr!**   
## <a name="related-rules"></a>Verwandte Regeln  
 [CA2116: APTCA-Methoden sollten nur APTCA-Methoden aufrufen](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben von sicherem Richtlinien](/dotnet/standard/security/secure-coding-guidelines)   
 [Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)   
