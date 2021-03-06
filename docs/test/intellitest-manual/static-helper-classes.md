---
title: "Statische Hilfsklassen | Microsoft IntelliTest Test-Tool für Entwickler | Microsoft-Dokumentation"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Static helper classes
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: fe4c855f9fad611dd1131997a86143523f51a80e
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2018
---
# <a name="static-helper-classes"></a>Statische Hilfsklassen

IntelliTest bietet eine Reihe von statischen Hilfsklassen, die beim Erstellen von [parametrisierten Unittests](test-generation.md#parameterized-unit-testing) verwendet werden können:

* [PexAssume](#pexassume): wird verwendet, um Annahmen auf Eingaben zu definieren und eignet sich zum Filtern unerwünschter Eingaben
* [PexAssert](#pexassert): eine einfache Assertionsklasse, die Sie zum Testen verwenden können, wenn Ihr Testframework keine Assertionsklasse zur Verfügung stellt
* [PexChoose](#pexchoose): ein Datenstrom von zusätzlichen Testeingaben, der von IntelliTest verwaltet wird
* [PexObserve](#pexobserve): protokolliert konkrete Werte und überprüft diese optional im generierten Code

Einige Klassen ermöglichen Ihnen eine Low-Level-Interaktion mit dem Ansatzpunktmodul von IntelliTest:

* [PexSymbolicValue](#pexsymbolicvalue): Hilfsprogramme zum Überprüfen oder Ändern von symbolischen Einschränkungen für Variablen

<a name="pexassume"></a>
## <a name="pexassume"></a>PexAssume

Eine statische Klasse zum Ausdrücken von Annahmen, wie z.B. [Vorbedingungen](test-generation.md#precondition) in [parametrisierten Unittests](test-generation.md#parameterized-unit-testing).
Mit den Methoden dieser Klasse können unerwünschte Testeingaben herausgefiltert werden.

Wenn die angenommene Bedingung für einige Testeingaben nicht erfüllt ist, wird eine **PexAssumeFailedException** ausgelöst. Dies bewirkt, dass den Test ohne Benachrichtigung ignoriert wird.

**Beispiel**

Der folgende parametrisierte Test berücksichtigt **j = 0** nicht:

```
public void TestSomething(int i, int j) {
     PexAssume.AreNotEqual(j, 0);
     int k = i/j;
     ...
}
```

**Hinweise**

Der obige Code ist fast äquivalent zu:

```
     if (j==0)
          return;
```

mit dem Unterschied, dass das Fehlschlagen von **PexAssume** zu keinen Testfällen führt. Im Falle einer **if**-Anweisung generiert IntelliTest einen separaten Testfall, um den **then**-Branch der **if**-Anweisung abzudecken.

**PexAssume** enthält auch spezialisierte geschachtelte Klassen für Annahmen für Zeichenfolgen, Arrays und Sammlungen.

<a name="pexassert"></a>
## <a name="pexassert"></a>PexAssert

Eine statische Klasse zum Ausdrücken von Assertionen, wie z.B. [Nachbedingungen](test-generation.md#postcondition) in [parametrisierten Unittests](test-generation.md#parameterized-unit-testing).

Wenn die angenommene Bedingung für eine bestimmte Testeingabe nicht erfüllt ist, wird eine **PexAssertFailedException** ausgelöst, was dazu führt, dass der Test fehlschlägt.

**Beispiel**

Im Folgenden wird bestätigt, dass der absolute Wert einer ganzen Zahl positiv ist:

```
public void TestSomething(int i) {
     int j = Maths.Abs(i);
     PexAssert.IsTrue(j >= 0);
     ...
}
```

<a name="pexchoose"></a>
## <a name="pexchoose"></a>PexChoose

Eine statische Klasse, die zusätzliche Eingabewerte für einen Test bereitstellt, die dazu verwendet werden können, [parametrisierte Pseudoobjekte](input-generation.md#parameterized-mocks) zu implementieren.

Mit der **PexChoose**-Klasse kann nicht ermittelt werden, ob ein Text für bestimmte Eingabewerte erfolgreich ist oder fehlschlägt. **PexChoose** liefert nur Eingabewerte, die auch als *Auswahlwerte* bezeichnet werden. Der Benutzer muss weiterhin die Eingabewerte einschränken und Assertionen schreiben, um zu definieren, wann ein Test erfolgreich ist bzw. fehlschlägt.

**Betriebsmodi**

Die **PexChoose**-Klasse kann in zwei Modi betrieben werden:

* Während der IntelliTest eine symbolische Analyse des Tests und des getesteten Codes während der [Eingabegeneration](input-generation.md) durchführt, gibt die Auswahl beliebige Werte zurück und IntelliTest verfolgt nach, wie jeder Wert im Test und dem getesteten Code verwendet wird. IntelliTest generiert relevante Werte, um unterschiedliche Ausführungspfade im Test und dem getesteten Code auszulösen.

* Der Choice-Anbieter richtet den generierten Code für bestimmte Testfälle auf eine bestimmte Weise ein, damit die erneute Ausführung eines solchen Testfalls spezifische Auswahlwerte erstellt, um einen bestimmten Ausführungspfad auszulösen.

**Verwendung**

* Machen Sie einen einfachen Aufruf an **PexChoose.Value**, um einen neuen Wert zu generieren:

```
public int Foo() {
    return PexChoose.Value<int>("foo");
}
```

<a name="pexobserve"></a>
## <a name="pexobserve"></a>PexObserve

Eine statische Klasse zum Protokollieren benannter Werte.

Wenn IntelliTest den Code untersucht, wird **PexObserve** verwendet, um die berechneten Werte mithilfe von deren formatierten Zeichenfolgendarstellungen aufzuzeichnen. Diesen Werten werden eindeutige Namen zugeordnet.

```
PexObserve.Value<string>("result", result);
```

**Beispiel**

```
// product code
public static class MathEx {
     public static int Square(int value) { return value * value; }
}


// fixture
[TestClass]
public partial class MathExTests {
     [PexMethod]
     public int SquareTest(int a) {
        int result = MathEx.Square(a); 
        // storing result
        return result;
     }
}
```

<a name="pexsymbolicvalue"></a>
## <a name="pexsymbolicvalue"></a>PexSymbolicValue

Eine statische Klasse, die verwendet wird, um Einschränkungen für Parameter zu ignorieren, und symbolischen Informationen zu drucken, die Werten zugeordnet wurden.

**Verwendung**

Normalerweise versucht IntelliTest alle Ausführungspfade des Codes während der Ausführung abzudecken. Allerdings sollte es, besonders bei der Berechnung von Annahmen und Assertionen, nicht alle möglichen Fälle untersuchen.

**Beispiel**

Dieses Beispiel zeigt die Implementierung der **PexAssume.Arrays.ElementsAreNotNull**-Methode. In dieser Methode ignorieren Sie die Einschränkungen für die Länge des Arraywerts, um zu vermeiden, dass IntelliTest versucht, verschiedene Größen des Arrays zu generieren. Die Einschränkungen werden nur hier ignoriert. Wenn sich der getestete Code für verschiedene Arraylängen unterschiedlich verhält, kann IntelliTest keine verschieden großen Arrays von den Einschränkungen des getesteten Codes generieren.

```
public static void AreElementsNotNull<T>(T[] value)
    where T : class
{
    PexAssume.NotNull(value);
    // the followings prevents the exploration of all array lengths
    int len = PexSymbolicValue.Ignore<int>(value.Length);

    // building up a boolean value as follows prevents exploration
    // of all combinations of non-null (instead, there are just two cases)
    bool anyNull = false;
    for (int i = 0; i < len; ++i)
        anyNull |= value[i] == null;

    // was any element null?
    if (anyNull)
        PexAssume.Fail("some element of array is a null reference");
}
```

## <a name="got-feedback"></a>Sie möchten Feedback geben?

Posten Sie Ihre Ideen und Clusterfunktion Anforderungen auf **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
