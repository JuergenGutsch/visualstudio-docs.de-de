---
title: Eigenschaften der Formen vom Typ Port | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.port
helpviewer_keywords: Domain-Specific Language, port shape
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8d8059d6399f4bb6e9df988fb5ef24eef9b8f096
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="properties-of-port-shapes"></a>Eigenschaften von Anschlussformen
Sie können Formen vom Typ Port verwenden, Domänenklassen in der generierten Designer dargestellt.  
  
 Weitere Informationen finden Sie unter [zum Definieren einer domänenspezifischen Sprache](../modeling/how-to-define-a-domain-specific-language.md). Weitere Informationen zum Verwenden dieser Eigenschaften finden Sie unter [anpassen und Erweitern einer domänenspezifischen Sprache](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 Formen vom Typ Port haben Eigenschaften, die in der folgenden Tabelle aufgeführt sind.  
  
|Eigenschaft|Beschreibung|Standard|  
|--------------|-----------------|-------------|  
|Füllfarbe|Die Füllfarbe dieser Form.|Weiß|  
|Farbverlauf Füllmodus|Der Farbverlauf Füllmodus dieser Form.|Horizontal|  
|Geometrie|Die Geometrie dieser Form (Rechteck, abgerundetes Rechteck, Ellipse oder Kreis).|Rechteck|  
|Hat die Standard-Verbindungspunkte|Wenn `True`verwenden der Form "oben, unten, links und rechts Verbindungspunkte im generierten-Designer.|False|  
|Umrissfarbe|Die Konturfarbe dieser Form.|Schwarz|  
|Dash Umrissstil|Das Gliederung Strichformat dieser Form (durchgezogen, Bindestrich, Punkt, DashDot, Strich oder Benutzerdefiniert).|Basis|  
|Umrissstärke|Die Stärke der Kontur dieser Form.|0.03125|  
|Textfarbe|Die Farbe, die für Text Decorator-Elementen verwendet wird, die mit dieser Form verknüpft sind.|Schwarz|  
|Zugriffsmodifizierer|Die Zugriffsebene der Klasse (`public` oder `internal`).|Public|  
|Benutzerdefinierte Attribute|Verwendet, um den Code Quellklasse Attribute hinzuzufügen, die von dieser Form generiert wird.|\<keine >|  
|Doppelter generiert abgeleitet|Wenn `True`, eine Basisklasse und eine partielle Klasse (zur Unterstützung von Anpassung außer Kraft) generiert werden. Weitere Informationen finden Sie unter [überschreiben und erweitern die generierte Klassen](../modeling/overriding-and-extending-the-generated-classes.md)|False|  
|Verfügt über benutzerdefinierte-Konstruktor|Wenn `True`, ein benutzerdefinierter Konstruktor im Quellcode bereitgestellt werden. Weitere Informationen finden Sie unter [überschreiben und erweitern die generierte Klassen](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Inheritance Modifier|Beschreibt die Art der Vererbung der Source Code-Klasse, die vom Port generiert wird (`none`, `abstract` oder `sealed`).|Keine|  
|Basis-Port|Die Basisklasse dieser Form.|(keine)|  
|name|Der Name dieser Form.|Aktuelle name|  
|Namespace|Der Namespace, der diese Form zugeordnet ist.|Aktuellen namespace|  
|Tool Tipp-Typ|Wie die QuickInfo definiert ist (fest, Variable oder keine). Wenn behoben, den Wert der `Fixed Tooltip Text` Eigenschaft wird als QuickInfo verwendet wird und wenn die Variable ist, klicken Sie dann die QuickInfo definiert ist in benutzerdefiniertem Code.|Keine|  
|Hinweise|Informelle Hinweise, die mit dieser Form verknüpft sind.|\<keine >|  
|Anfängliche Höhe|Die anfängliche Höhe dieser Form, in Zoll.|1|  
|Anfängliche Breite|Die anfängliche Breite dieser Form, in Zoll.|1.5|  
|Als Eigenschaft verfügbar gemachte Füllfarbe<br /><br /> Verfügbar gemachten Füllmodus Farbverlauf<br /><br /> Konturfarbe als Eigenschaft verfügbar gemacht.<br /><br /> Gliederung Strichformat als Eigenschaft verfügbar gemacht.<br /><br /> Umrissstärke als Eigenschaft bereitgestellt<br /><br /> Macht die Textfarbe|Wenn `True`, der Benutzer kann die angegebene Eigenschaft einer Form festlegen. Um dies festzulegen, mit der rechten Maustaste der Form "Definition, und klicken Sie auf **hinzufügen verfügbar gemachten**.|False|  
|Beschreibung|So dokumentieren Sie den generierten-Designer verwendet.|\<keine >|  
|Anzeigename|Der Name, der in der generierten Designer für diese Form angezeigt wird.|\<keine >|  
|Feste QuickInfo-Text|Der Text, der für eine feste QuickInfo verwendet wird.|\<keine >|  
|Hilfsschlüsselwort|Das Schlüsselwort, das zum Indizieren der F1-Hilfe für diese Form verwendet wird.|\<keine >|  
  
## <a name="see-also"></a>Siehe auch  
 [Domänenspezifische Sprache Tools Glossar](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)