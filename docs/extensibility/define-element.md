---
title: Definieren von Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Define
- Define element (VSCT XML schema)
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 35d33f0c440bce6d83c8a4712f0059d7f51a0ff0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="define-element"></a>Definieren von Element
Definiert ein Symbol Name / Wert-Paar. Dieses Symbol kann durch bedingten Attribute ausgewertet werden. Weitere Informationen finden Sie unter [bedingte Attribute](../extensibility/vsct-xml-schema-conditional-attributes.md). Siehe auch die [Element werden Symbole](../extensibility/symbols-element.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
<Define name="Mode" value="Standard" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Erforderlich. Der Name des Symbols:<br /><br /> Name = "Modus"|  
|Wert|Erforderlich. Der Wert des Symbols:<br /><br /> Wert = "Standard"|  
|Bedingung|Dies ist optional. Weitere Informationen finden Sie unter [bedingte Attribute](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[CommandTable-Element](../extensibility/commandtable-element.md)|Definiert die Elemente aus, die Befehle, die eine VSPackage bereitstellt, der integrierten Entwicklungsumgebung (IDE) darstellen. Beispielsweise Menüelemente, Menüs, Symbolleisten und Kombinationsfelder.|  
  
## <a name="example"></a>Beispiel  
  
```  
<Define name="DEMO_UI"/>  
<Define name="MODE" value="Standard"/>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [VSCT-Dateien (Visual Studio Command Table)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)