---
title: "Deinstallieren von Visual Studio für Mac | Microsoft-Dokumentation"
description: "Anleitung zum Deinstallieren von Visual Studio für Mac und dazugehörigen Tools"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 4EB95F75-BC2E-4982-9564-2975805712D8
ms.openlocfilehash: 193eebd4849e6a133ade1d14cb17d5b345199811
ms.sourcegitcommit: 24f81b8fb59722cf4a856005227f6a29bb2990cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="uninstalling-visual-studio-for-mac"></a>Deinstallieren von Visual Studio für Mac

Es gibt eine Reihe von Xamarin-Produkten einschließlich eigenständiger Apps wie Visual Studio für Mac, die die plattformübergreifende Anwendungsentwicklung ermöglichen.

Mit diesem Handbuch können Sie jedes Produkt einzeln deinstallieren, indem Sie zum entsprechenden Abschnitt navigieren. Das gesamte Xamarin-Toolset kann anhand dieser Anleitung deinstalliert werden.

Wenn Sie zuvor bereits Xamarin Studio auf Ihrem Computer installiert hatten, müssen Sie außer den nachfolgenden Schritten möglicherweise auch die Anleitung im [Deinstallationshandbuch](https://developer.xamarin.com/guides/cross-platform/getting_started/installation/uninstalling_xamarin/) auf developer.xamarin.com ausführen.

## <a name="uninstall-script"></a>Deinstallieren des Skripts

Sie können Visual Studio und die zugehörigen Komponenten auf einmal mithilfe des Deinstallationsskripts deinstallieren, das Sie [hier](https://raw.githubusercontent.com/MicrosoftDocs/visualstudio-docs/master/mac/resources/uninstall-vsmac.sh) finden.

Dieses Deinstallationsskript enthält die meisten Befehle, die Sie im Artikel finden. Es gibt zwei wichtigsten Auslassungen gegenüber dem Skript, die aufgrund von möglichen externen Abhängigkeiten nicht enthalten sind:

- **Deinstallation von Mono**
- **Deinstallieren von Android AVD**

Um das Skript auszuführen, führen Sie die folgenden Schritte durch:

1. Klicken Sie mit der rechten Maustaste auf das Skript, und wählen Sie **Speichern unter...** aus, um die Datei auf Ihrem Mac zu speichern.
2. Öffnen Sie das Terminal, und ändern Sie das Arbeitsverzeichnis, in das das Skript heruntergeladen wurde:

    ```bash
    $ cd /location/of/file
    ```
3. Machen Sie das Skript ausführbar, und führen Sie es mit **sudo** aus:

    ```bash
    $ chmod +x ./uninstall-vsmac.sh
    $ sudo ./uninstall-vsmac.sh
    ```
4. Löschen Sie schließlich das Deinstallationsskript.

## <a name="uninstall-visual-studio-for-mac"></a>Deinstallieren von Visual Studio für Mac

Der erste Schritt bei der Deinstallation von Visual Studio für Mac besteht darin, die **Visual Studio.app** im Verzeichnis **/Anwendungen** zu suchen und in den **Papierkorb** zu legen. Alternativ können Sie mit der rechten Maustaste darauf klicken und **In den Papierkorb legen** wie unten gezeigt auswählen:

![Visual Studio-Anwendung in den Papierkorb verschieben](media/uninstall-image1.png)

Durch das Löschen dieses App Bundles wird Visual Studio für Mac entfernt, obwohl es im Dateisystem möglicherweise noch andere Dateien im Zusammenhang mit Xamarin gibt.

Um alle Spuren von Visual Studio für Mac zu entfernen, sollten Sie die folgenden Befehle im Terminal ausführen:

```bash
sudo rm -rf "/Applications/Visual Studio.app"
rm -rf ~/Library/Caches/VisualStudio
rm -rf ~/Library/Preferences/VisualStudio
rm -rf "~/Library/Preferences/Visual Studio"
rm -rf ~/Library/Logs/VisualStudio
rm -rf ~/Library/VisualStudio
rm -rf ~/Library/Preferences/Xamarin/
rm -rf ~/Library/Developer/Xamarin
rm -rf "~/Library/Application Support/VisualStudio"
```

## <a name="uninstall-mono-sdk-mdk"></a>Deinstallieren des Mono SDK (MDK)

Mono ist eine Open-Source-Implementierung von Microsofts .NET Framework und wird von allen Xamarin-Produkten (Xamarin.iOS, Xamarin.Android und Xamarin.Mac) verwendet, damit diese Plattformen in C# entwickelt werden können.

> [!WARNING]
> Außerhalb von Visual Studio für Mac gibt es weitere Anwendungen, die ebenfalls Mono verwenden, z.B. Unity.
> Achten Sie darauf, dass es keine weiteren Abhängigkeiten mit Mono bestehen, bevor Sie es deinstallieren.

Um das Mono-Framework von einem Computer zu entfernen, führen Sie die folgenden Befehle im Terminal aus:

```bash
sudo rm -rf /Library/Frameworks/Mono.framework
sudo pkgutil --forget com.xamarin.mono-MDK.pkg
sudo rm -rf /etc/paths.d/mono-commands
```

## <a name="uninstall-xamarinandroid"></a>Deinstallieren von Xamarin.Android

Es gibt eine Anzahl von Elementen, die für die Installation und Verwendung von Xamarin.Android erforderlich sind, z.B. das Android SDK und das Java SDK.

Verwenden Sie die folgenden Befehle, um Xamarin.Android zu entfernen:

```bash
sudo rm -rf /Developer/MonoDroid
rm -rf ~/Library/MonoAndroid
sudo pkgutil --forget com.xamarin.android.pkg
sudo rm -rf /Library/Frameworks/Xamarin.Android.framework
```

### <a name="uninstall-android-sdk-and-java-sdk"></a>Deinstallieren des Android SDK und des Java SDK

Das Android SDK ist für die Entwicklung von Android-Anwendungen erforderlich. Um alle Bestandteile des Android SDK vollständig zu entfernen, suchen Sie die Datei unter **~/Library/Developer/Xamarin/**, und verschieben Sie sie in den **Papierkorb**.

Java SDK (JDK) muss nicht deinstalliert werden, da es unter Mac OS X/macOS bereits vorab installiert ist.

### <a name="uninstall-android-avd"></a>Deinstallieren von Android-AVDs

> [!WARNING]
> Es gibt weitere Anwendungen außerhalb von Visual Studio für Mac, die ebenfalls Android-AVDs und diese zusätzlichen Android-Komponenten verwenden, z.B. Android Studio.
> Das Entfernen dieses Verzeichnisses kann dazu führen, dass Projekte in Android Studio unterbrochen werden. 

Verwenden Sie zum Entfernen aller Android-AVDs und weiteren Android Komponenten den folgenden Befehl:

```bash
rm -rf ~/.android
```

Um nur Android-AVDs zu entfernen, verwenden Sie den folgenden Befehl:

```bash
rm -rf ~/.android/avd
```

 

## <a name="uninstall-xamarinios"></a>Deinstallieren von Xamarin.iOS

Xamarin.iOS ermöglicht die Entwicklung von iOS-Anwendungen mit C# oder F# in Visual Studio für Mac.

Der Xamarin-Buildhost wurde auch in früheren Versionen von Xamarin.iOS automatisch installiert, um die iOS-Entwicklung in Visual Studio zu ermöglichen. Um beides auf einem Computer zu deinstallieren, führen Sie die folgenden Schritte aus:

Führen Sie die folgenden Befehle im Terminal aus, um alle Xamarin.iOS-Dateien aus einem Dateisystem zu entfernen:

```bash
rm -rf ~/Library/MonoTouch
sudo rm -rf /Library/Frameworks/Xamarin.iOS.framework
sudo rm -rf /Developer/MonoTouch
sudo pkgutil --forget com.xamarin.monotouch.pkg
sudo pkgutil --forget com.xamarin.xamarin-ios-build-host.pkg
sudo pkgutil --forget com.xamarin.xamarin.ios.pkg
```

## <a name="uninstall-xamarinmac"></a>Deinstallieren von Xamarin.Mac

Nachdem Sie Visual Studio für Mac erfolgreich deinstalliert haben, können Sie Xamarin.Mac und dessen Lizenz mithilfe der folgenden beiden Befehle vom Computer entfernen:

```bash
sudo rm -rf /Library/Frameworks/Xamarin.Mac.framework
rm -rf ~/Library/Xamarin.Mac
```

## <a name="uninstall-workbooks-and-inspector"></a>Deinstallieren von Workbooks und Inspector

Ab 1.2.2 kann Xamarin Workbooks & Inspektor im Terminal deinstalliert werden, indem Sie Folgendes ausführen:

```bash
sudo /Library/Frameworks/Xamarin.Interactive.framework/Versions/Current/uninstall
```

Für frühere Versionen müssen Sie manuell Folgendes entfernen:

* Löschen Sie die Workbooks-App unter `"/Applications/Xamarin Workbooks.app"`.
* Löschen Sie die Inspector-App unter `"Applications/Xamarin Inspector.app"`.
* Löschen Sie die Add-ins `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Interactive"` und `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Inspector"`.
* Löschen Sie Inspector und die unterstützenden Dateien hier: `/Library/Frameworks/Xamarin.Interactive.framework` und `/Library/Frameworks/Xamarin.Inspector.framework`.

# <a name="uninstall-the-xamarin-profiler"></a>Deinstallieren von Xamarin Profiler

```bash
sudo rm -rf "/Applications/Xamarin Profiler.app"
```

## <a name="uninstall-the-visual-studio-installer"></a>Deinstallieren Sie den Visual Studio-Installer.

Verwenden Sie die folgenden Befehle, um alle Spuren des Xamarin-Universal-Installer zu entfernen:

```bash
rm -rf ~/Library/Caches/XamarinInstaller/
rm -rf ~/Library/Caches/VisualStudioInstaller/
rm -rf ~/Library/Logs/XamarinInstaller/
rm -rf ~/Library/Logs/VisualStudioInstaller/
rm -rf ~/Library/Preferences/Xamarin/
rm -rf "~/Library/Preferences/Visual Studio/"
```
