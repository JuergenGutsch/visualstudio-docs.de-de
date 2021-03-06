---
title: "CA2133: Delegaten müssen Binden an Methoden mit konsistenter Transparenz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d5e5d391fc11fbefbe1f3cef6ee1512ab02d6b00
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133: Delegaten müssen an Methoden mit konsistenter Transparenz gebunden werden
|||  
|-|-|  
|TypeName|DelegatesMustBindWithConsistentTransparency|  
|CheckId|CA2133|  
|Kategorie|Microsoft.Security|  
|Unterbrechende Änderung|Breaking|  
  
> [!NOTE]
>  Diese Warnung wird nur auf Code angewendet werden, die die CoreCLR (die Version der CLR, die speziell für Silverlight-Webanwendungen ist) ausgeführt wird.  
  
## <a name="cause"></a>Ursache  
 Diese Warnung wird ausgelöst, auf eine Methode, die einen Delegaten gebunden, die mit der <xref:System.Security.SecurityCriticalAttribute> an eine Methode, die transparent oder mit markiert, die <xref:System.Security.SecuritySafeCriticalAttribute>. Die Warnung wird auch für eine Methode ausgelöst, die einen transparenten oder sicherheitsrelevanten Delegaten an eine wichtige Methode bindet.  
  
## <a name="rule-description"></a>Regelbeschreibung  
 Delegattypen und die Methoden, denen sie zum Binden müssen konsistenten Transparenz wahren aufweisen. Transparente und sicherheitsrelevanten Delegaten können nur an andere Methoden transparenten oder sicherheitsrelevanten gebunden werden. Auf ähnliche Weise können wichtige Delegaten nur an wichtige Methoden binden. Diese Bindungsregeln sicher, dass der einzige Code, mit der eine Methode über einen Delegaten aufgerufen werden kann auch die gleiche Methode direkt aufgerufen haben kann. Z. B. verhindern Bindungsregeln transparenten Code sicherheitsrelevanter Code direkt über einen transparenten Delegaten aufrufen.  
  
## <a name="how-to-fix-violations"></a>Behandeln von Verstößen  
 Um einen Verstoß gegen diese Warnung zu beheben, ändern Sie die Transparenz des Delegaten oder der Methode, die gebunden wird, damit die Transparenz der beiden sind äquivalent.  
  
## <a name="when-to-suppress-warnings"></a>Wann sollten Warnungen unterdrückt werden?  
 Unterdrücken Sie keine Warnung dieser Regel.  
  
### <a name="code"></a>Code  
 [!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]