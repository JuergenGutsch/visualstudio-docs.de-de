---
title: 'Vorgehensweise: Verwenden von bearbeiten und Fortfahren (c#) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: fe77428d1d9cfb5ff12554e87ec9afe15d6c86b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-edit-and-continue-c"></a>Gewusst wie: Verwenden von "Bearbeiten und Fortfahren" (C#)
Mit Bearbeiten und Fortfahren für C# können Sie beim Debuggen Codeänderungen im Unterbrechungsmodus vornehmen. Die Änderungen können übernommen werden, ohne die Debugsitzung anhalten und neu starten zu müssen.  
  
 Bearbeiten und Fortfahren wird automatisch aufgerufen, wenn Sie im Unterbrechungsmodus Änderungen vornehmen, und wählen Sie dann eine Debugger die Ausführung Befehl, wie z. B. **Fortfahren**, **Schritt**, oder **nächste Anweisung festlegen**, oder eine Funktion in einem Debuggerfenster auswerten.  
  
> [!NOTE]
>  Bearbeiten und Fortfahren wird nicht unterstützt, beim Debuggen von Code, gemischtem systemeigenem/verwaltetem Code oder SQL Server common Language Runtime (CLR) Integration Code optimieren. Informationen zu anderen nicht unterstützten Szenarien finden Sie unter [unterstützte Codeänderungen (C#- und Visual Basic)](../debugger/supported-code-changes-csharp.md). Wenn Sie versuchen, Anwenden von Änderungen am Code in einem solchen Szenario, zeigt der Debugger ein Dialogfeld mit dem Hinweis angezeigt, die bearbeiten und Fortfahren nicht unterstützt.  
  
### <a name="to-invoke-edit-and-continue-automatically"></a>So rufen Sie Bearbeiten und Fortfahren automatisch auf  
  
1.  Nehmen Sie im Unterbrechungsmodus eine Änderung am Quellcode vor.  
  
2.  Aus der **Debuggen** Menü klicken Sie auf **Fortfahren**, **Schritt**, oder **nächste Anweisung festlegen** oder Werten Sie eine Funktion in einem Debuggerfenster.  
  
     Der neue Code wird kompiliert, und das Debuggen wird mit neuem Code fortgesetzt. Einige Änderungen werden von Bearbeiten und Fortfahren nicht unterstützt. Weitere Informationen finden Sie unter [unterstützte Codeänderungen (C#- und Visual Basic)](../debugger/supported-code-changes-csharp.md).  
  
### <a name="to-enabledisable-edit-and-continue"></a>So aktivieren bzw. deaktivieren Sie "Bearbeiten und Fortfahren"  
  
1.  Klicken Sie im Menü **Extras** auf **Optionen**.  
  
2.  In der **Optionen** Dialogfeld erweitern Sie die **Debuggen** Knoten, und wählen **bearbeiten und Fortfahren**.  
  
3.  In der **Optionen** Dialogfeld **bearbeiten und Fortfahren** aktivieren oder Deaktivieren der **bearbeiten und Fortfahren aktivieren** Kontrollkästchen.  
  
     Die Einstellungen werden beim Neustarten der Debugsitzung aktiv.  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten Sie und fortfahren Sie (Visual c#)](../debugger/edit-and-continue-visual-csharp.md)   
 [Unterstützte Codeänderungen (C#- und Visual Basic)](../debugger/supported-code-changes-csharp.md)   