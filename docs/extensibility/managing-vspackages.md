---
title: Verwalten von VSPackages | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3c3201c032d0cae645460e614b6d4138297e4a93
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="managing-vspackages"></a>Verwalten von VSPackages
In den meisten Fällen müssen Sie nicht zum Verwalten von VSPackages, da die Projekt- und Elementvorlagen registrieren, und Laden Sie das Paket automatisch Sorge. In einigen Fällen müssen Sie jedoch ein wenig mehr erfahren, um das Paket zu verwalten.  
  
## <a name="using-the-experimental-instance"></a>Verwenden die experimentelle Instanz  
 Weitere Informationen zu der experimentellen Instanz finden Sie unter [die experimentelle Instanz](../extensibility/the-experimental-instance.md).  
  
## <a name="registering-and-unregistering-vspackages"></a>Registrieren und Aufheben der Registrierung von VSPackages  
 Um herauszufinden, wie die Registrierung und Aufheben der Registrierung von VSPackages und anderen Typen von Erweiterung, finden Sie unter [registrieren und Aufheben der Registrierung von VSPackages](../extensibility/registering-and-unregistering-vspackages.md).  
  
## <a name="loading-a-vspackage"></a>Laden eine VSPackage  
 VSPackages kann auf Autoload eines bestimmten festgelegt werden, die CMDUICONTEXT GUID eingeschaltet ist. Weitere Informationen finden Sie unter [Laden von VSPackages](../extensibility/loading-vspackages.md).  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>Mithilfe von AsyncPackage VSPackages im Hintergrund geladen  
 Die Klasse AsyncPackage ermöglicht Paket laden in einem Hintergrundthread für bessere Reaktionsfähigkeit der Benutzeroberfläche in Visual Studio. Weitere Informationen finden Sie unter [wie: Verwenden von AsyncPackage Load-VSPackages im Hintergrund](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md).  
  
## <a name="rule-based-ui-context-for-extensions"></a>Regel-basierte Benutzeroberflächenkontext für Erweiterungen  
 Benutzeroberflächen-Kontexte regelbasierte Autoren Erweiterung zum Definieren der präzisen Bedingungen, unter dem eine UI-Kontext aktiviert ist, und zugeordnete VSPackages geladen. Weitere Informationen finden Sie unter [Vorgehensweise: Benutzeroberflächenkontext für Visual Studio-Erweiterungen verwenden regelbasierte](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md).  
  
## <a name="diagnosing-extension-performance"></a>Diagnostizieren der Leistung der Erweiterung  
Erweiterungen können Start- und Lösung ladeleistung auswirken. Erfahren Sie, wie Visual Studio-Erweiterung Impact berechnet wird und wie es lokal analysiert werden kann zum Testen, ob eine Erweiterung als eine Erweiterung mit Auswirkungen auf Leistung angezeigt werden kann. Weitere Informationen finden Sie unter [wie: Diagnose Erweiterung Leistung](how-to-diagnose-extension-performance.md). 
  
## <a name="troubleshooting-vspackages"></a>Problembehandlung bei VSPackages  
 Ermitteln Sie die Techniken der Problembehandlung von VSPackages, die nicht geladen oder treten Fehler: [Problembehandlung VSPackages](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>Siehe auch  
 [VSPackages](../extensibility/internals/vspackages.md)