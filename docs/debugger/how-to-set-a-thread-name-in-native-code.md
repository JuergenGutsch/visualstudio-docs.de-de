---
title: 'Vorgehensweise: Festlegen eines Threadnamens in systemeigenem Code | Microsoft Docs'
ms.custom: 
ms.date: 04/27/2017
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
helpviewer_keywords:
- debugging [C++], threads
- SetThreadName function
- threading [Visual Studio], names
- thread names
- debugging [Visual Studio], threads
ms.assetid: c85d0968-9f22-4d69-87f4-acca2ae777b8
caps.latest.revision: "37"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 34340fc1a56c3b35c626cbd48157b1b09d0cd91d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-thread-name-in-native-code"></a>Gewusst wie: Festlegen eines Threadnamens in nativem Code
Das Benennen von Threads ist in allen Editionen von Visual Studio möglich. Benennen von Threads ist nützlich zum Nachverfolgen der Threads in der **Threads** Fenster.

Verwenden Sie zum Festlegen eines Threadnamens im Programm die `SetThreadName` -Funktion, wie im folgenden Codebeispiel dargestellt. Der Threadname wird in den Thread kopiert, damit der Arbeitsspeicher für den `threadName` -Parameter freigegeben werden kann.  
  
## <a name="example"></a>Beispiel  
  
```C++  
//  
// Usage: SetThreadName ((DWORD)-1, "MainThread");  
//  
#include <windows.h>  
const DWORD MS_VC_EXCEPTION = 0x406D1388;  
#pragma pack(push,8)  
typedef struct tagTHREADNAME_INFO  
{  
    DWORD dwType; // Must be 0x1000.  
    LPCSTR szName; // Pointer to name (in user addr space).  
    DWORD dwThreadID; // Thread ID (-1=caller thread).  
    DWORD dwFlags; // Reserved for future use, must be zero.  
 } THREADNAME_INFO;  
#pragma pack(pop)  
void SetThreadName(DWORD dwThreadID, const char* threadName) {  
    THREADNAME_INFO info;  
    info.dwType = 0x1000;  
    info.szName = threadName;  
    info.dwThreadID = dwThreadID;  
    info.dwFlags = 0;  
#pragma warning(push)  
#pragma warning(disable: 6320 6322)  
    __try{  
        RaiseException(MS_VC_EXCEPTION, 0, sizeof(info) / sizeof(ULONG_PTR), (ULONG_PTR*)&info);  
    }  
    __except (EXCEPTION_EXECUTE_HANDLER){  
    }  
#pragma warning(pop)  
}  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Multithreadanwendungen](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Anzeigen von Daten im Debugger](../debugger/viewing-data-in-the-debugger.md)   
 [Gewusst wie: Festlegen eines Threadnamens in verwaltetem Code](../debugger/how-to-set-a-thread-name-in-managed-code.md)