---
title: "Gewusst wie: Installieren der verteilbaren Visual Studio Tools for Office Runtime"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Installieren von Office-Entwicklungstools in Visual Studio"
  - "Office-Laufzeit [Office-Entwicklung in Visual Studio]"
ms.assetid: ac7a9ad3-e810-4d7f-a0e2-9992c9036b8d
caps.latest.revision: 94
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 93
---
# Gewusst wie: Installieren der verteilbaren Visual Studio Tools for Office Runtime
  Visual Studio 2010\-Tools für Office\-Laufzeit muss auf jedem Computer installiert sein, auf dem Projektmappen ausgeführt werden, die mit Microsoft Office Developer Tools in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] erstellt wurden.  Die Laufzeit wird automatisch installiert, wenn Sie [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] und Microsoft Office installieren.  Weitere Informationen finden Sie unter [Laufzeitinstallationsszenarios für Visual Studio Tools for Office](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md).  
  
 Sie müssen möglicherweise die Anweisungen zur manuellen Installation weiter unten in den folgenden Situationen befolgen:  
  
-   Sie müssen [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] auf einem Server installieren.  Sie möchten z. B. die <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>\-Klasse verwenden, um Lösungen auf Dokumentebene auf einem Server zu verwalten.  
  
-   Sie müssen die Laufzeit auf einem Computer installieren, auf dem bereits alle anderen erforderlichen Komponenten für Office\-Lösungen installiert wurden.  
  
    > [!NOTE]  
    >  Sie müssen auf dem Entwicklungscomputer über Administratorrechte verfügen, um .NET Framework und [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] zu installieren.  
  
### So installieren Sie Visual Studio Tools for Office Runtime  
  
1.  Installieren Sie [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] oder höher.  
  
    -   Informationen zum Herunterladen von [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] finden Sie unter [Microsoft .NET Framework 4 \(Webinstaller\)](http://go.microsoft.com/fwlink/?LinkId=178957).  
  
    -   Informationen zum Herunterladen von [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)] finden Sie unter [Microsoft .NET Framework 4 Client Profile \(Webinstaller\)](http://go.microsoft.com/fwlink/?LinkId=178958).  
  
    -   Informationen zum Herunterladen von [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] finden Sie unter [Microsoft .NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653).  
  
2.  Führen Sie vstor\_redist.exe aus, um [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] zu installieren.  
  
     Sie können diese Setupdateien unter [Visual Studio 2010\-Tools für Office\-Laufzeit](http://go.microsoft.com/fwlink/?LinkId=140384) herunterladen.  Die erforderlichen Komponenten für [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] stimmen mit denen für .NET Framework überein.  
  
     Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] enthält Language Packs.  Wenn Sie für Windows andere Spracheinstellungen als Englisch festgelegt haben, können Sie Laufzeitmeldungen in der Sprache anzeigen, die Sie für Windows verwenden.  Wenn Endbenutzer [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] installieren und dann die Projektmappen auf Windows\-Installationen ausführen, die andere Spracheinstellungen als Englisch verwenden, werden Laufzeitmeldungen entsprechend in derselben Sprache wie Windows angezeigt.  In einigen Fällen benötigen Sie möglicherweise zusätzliche Language Packs.  Beispielsweise benötigen Sie möglicherweise weitere Language Packs, wenn Ihre Windows\-Version mehr als eine Spracheinstellung verwendet oder wenn Sie auf eine andere Sprache umstellen, nachdem Sie [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] bereits installiert haben.  Language Packs finden Sie unter [Microsoft Visual Studio 2010\-Tools für Office Language Pack \(Laufzeitversion 4.0\)](http://go.microsoft.com/fwlink/?LinkId=140386).  
  
## Siehe auch  
 [Erste Schritte &#40;Office-Entwicklung in Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Konfigurieren eines Computers zum Entwickeln von Office-Lösungen](../vsto/configuring-a-computer-to-develop-office-solutions.md)   
 [Gewusst wie: Konfigurieren eines Computers zum Entwickeln von Office-Projektmappen](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)   
 [Gewusst wie: Installieren von primären Interopassemblys für Office](../vsto/how-to-install-office-primary-interop-assemblies.md)   
 [Verwalten von Dokumenten auf einem Server mit der ServerDocument-Klasse](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Bereitstellen einer Office-Projektmappe](../vsto/deploying-an-office-solution.md)  
  
  