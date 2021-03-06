---
title: '&lt;FileAssociation&gt; Element (ClickOnce-Anwendung) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <fileAssociation> element [ClickOnce application manifest]
- manifests [ClickOnce], fileAssociation element
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
caps.latest.revision: "8"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: bd5d7ed1a37923cefc4a6b7975610b6016fd0ae6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltfileassociationgt-element-clickonce-application"></a>&lt;FileAssociation&gt; Element (ClickOnce-Anwendung)
Gibt eine Erweiterung der Anwendung zugeordnet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elemente und Attribute  
 Das `fileAssociation`-Element ist optional. Das Element weist folgende Attribute.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`extension`|Erforderlich. Die Dateierweiterung der Anwendung zugeordnet werden soll.|  
|`description`|Erforderlich. Eine Beschreibung des Dateityps für die Verwendung von der Shell.|  
|`progid`|Erforderlich. Ein Name, die den Dateityp eindeutig identifiziert.|  
|`defaultIcon`|Erforderlich. Gibt das Symbol für Dateien mit dieser Erweiterung verwenden. Die Symboldatei muss angegeben werden, mithilfe der [ \<Datei > Element](../deployment/file-element-clickonce-application.md) innerhalb der [ \<Assembly >-Element](../deployment/assembly-element-clickonce-application.md) , enthält dieses Element.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element muss enthalten einen XML-Namespaceverweis auf "Urn: Schemas-Microsoft-com:clickonce.v1". Wenn die `<fileAssociation>` Element verwendet wird, müssen sie nach dem stammen die `<application>` in seinem übergeordneten Element [ \<Assembly >-Element](../deployment/assembly-element-clickonce-application.md).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]überschreibt keine vorhandenen dateizuordnungen. Eine ClickOnce-Anwendung kann jedoch die Dateierweiterung für den aktuellen Benutzer nur überschreiben. Nach der Deinstallation von ClickOnce-Anwendung ClickOnce löscht die dateizuordnung für den Benutzer und die Zuordnung pro Computer wieder aktiv ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, `fileAssociation` Elemente in einer Anwendung für einen Text-Editor-Anwendung bereitgestellt, mit manifest [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Dieses Codebeispiel enthält auch die [ \<Datei >-Element](../deployment/file-element-clickonce-application.md) erforderlich die `defaultIcon` Attribut.  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ClickOnce-Anwendungsmanifest](../deployment/clickonce-application-manifest.md)