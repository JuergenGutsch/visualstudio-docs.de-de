---
title: "CA2210: Assemblys müssen gültige starke Namen aufweisen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
helpviewer_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
ms.assetid: 8ed33d1c-8ec6-4b47-a692-e22dc8693088
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 066c78158b688db8164a5ebf23dbe957c7c324ba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ca2210-assemblies-should-have-valid-strong-names"></a>CA2210: Assemblys müssen gültige starke Namen aufweisen
|||  
|-|-|  
|TypeName|AssembliesShouldHaveValidStrongNames|  
|CheckId|CA2210|  
|Kategorie|Microsoft.Design|  
|Unterbrechende Änderung|Nicht unterbrechende Änderung|  
  
## <a name="cause"></a>Ursache  
 Eine Assembly ist nicht mit einem starken Namen signiert der starke Name konnte nicht überprüft werden, oder der starke Name ist nicht mehr gültig ist, ohne die aktuellen registrierungseinstellungen für die des Computers.  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Diese Regel ruft ab und überprüft den starken Namen einer Assembly. Eine Verletzung tritt auf, wenn Folgendes zutrifft:  
  
-   Die Assembly keinen starken Namen.  
  
-   Die Assembly, die nach dem Signieren geändert wurde.  
  
-   Die Assembly wird verzögert signiert.  
  
-   Die Assembly wurde nicht ordnungsgemäß signiert oder Fehler beim Signieren.  
  
-   Die Assembly benötigt registrierungseinstellungen Überprüfung übergeben. Beispielsweise wurde das Strong Name-Tool (Sn.exe) zum Überspringen der Überprüfung der Assembly verwendet.  
  
 Der starke Name schützt Clients vor dem versehentlichen Laden einer manipulierten Assembly. Assemblys ohne starke Namen sollten nur in ganz bestimmten Szenarien bereitgestellt werden. Wenn Sie nicht einwandfrei signierte Assemblys freigeben oder verteilen, kann die Assembly manipuliert werden, die Common Language Runtime lädt die Assembly unter Umständen nicht, oder der Benutzer muss die Überprüfung auf dem Computer deaktivieren. Eine Assembly ohne starken Namen besitzt die folgenden Nachteile:  
  
-   Die Ursprünge können nicht überprüft werden.  
  
-   Die common Language Runtime kann nicht Benutzer benachrichtigen, wenn der Inhalt der Assembly geändert wurden.  
  
-   Es kann im globalen Assemblycache geladen werden.  
  
 Beachten Sie, dass beim Laden und analysieren eine Assembly verzögert signiert, müssen Sie die Überprüfung der Assembly deaktivieren.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 **So erstellen eine Schlüsseldatei**  
  
 Verwenden Sie eine der folgenden Verfahren aus:  
  
-   Verwenden Sie die Assembly Linker-Tool (Al.exe) bereitgestellt werden, indem Sie die [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK.  
  
-   Für die [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , Version 1.0 oder Version 1.1, verwenden Sie entweder die <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> oder <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> Attribut.  
  
-   Für die [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)], verwenden Sie entweder die `/keyfile` oder `/keycontainer` Compileroption [/keyfile (Schlüssel angeben oder öffentlichen/privaten Schlüsselpaars zum Signieren einer Assembly)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly) oder  [ /keycontainer (Geben Sie einen Schlüsselcontainer zum Signieren einer Assembly)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly) -Linkeroption in C++).  
  
 **Zum Signieren der Assembly mit einem starken Namen in Visual Studio**  
  
1.  In [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], öffnen Sie die Projektmappe.  
  
2.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **Eigenschaften.**  
  
3.  Klicken Sie auf die **Signierung** , und wählen Sie die **zum Signieren der Assembly** Kontrollkästchen.  
  
4.  Von **Schlüsseldatei mit starkem Namen auswählen**Option **neu**.  
  
     Die **Schlüssel für einen starken Namen erstellen** Fenster angezeigt.  
  
5.  In **Schlüsseldateiname**, geben Sie einen Namen für Ihre Schlüssel mit starkem Namen.  
  
6.  Wählen Sie, ob der Schlüssel mit einem Kennwort geschützt, und klicken Sie dann auf **OK**.  
  
7.  In **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und klicken Sie dann auf **erstellen**.  
  
 **Zum Signieren der Assembly mit einem starken Namen außerhalb von Visual Studio**  
  
-   Verwenden Sie das strong Name-Tool (Sn.exe), die von bereitgestellten der [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK. Weitere Informationen finden Sie unter [Sn.exe (Strong Name-Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool).  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Nur eine Warnung dieser Regel zu unterdrücken, wenn die Assembly in einer Umgebung verwendet wird, den Inhalt manipulieren nicht relevant ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName>   
 <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>   
 [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)   
 [Sn.exe (Strong Name-Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool)