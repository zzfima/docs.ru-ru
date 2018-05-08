---
title: Безопасность и конфликты
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfc4d9e9ba3653bd1a762767e3c39a4f62e587a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="security-and-race-conditions"></a>Безопасность и конфликты
Другой областью проблемных является возможность бреши в гонки безопасности. Существует несколько способов, в которых это может произойти. Нижеследующие подразделы описывают некоторые основные ловушки, которые разработчик должен обойти.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Состояния гонки в методе Dispose  
 Если класс **Dispose** метод (Дополнительные сведения см. в разделе [мусора](../../../docs/standard/garbage-collection/index.md)) — не синхронизирован, существует возможность, код очистки в **Dispose** может выполняться более чем один раз, как показано в следующем примере.  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()   
{  
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 Так как это **Dispose** реализации не синхронизирована, то возможна `Cleanup` будет вызвана сначала одним потоком, а затем второй поток перед `_myObj` задано значение **null**. Является ли это угроза безопасности зависит от того, что происходит при `Cleanup` выполнении кода. Основная проблема, связанная с несинхронизированные **Dispose** реализациями относится к использованию дескрипторов ресурсов, таких как файлы. Неверное удаление может привести неправильное дескриптора для использования, что часто приводит к уязвимости системы безопасности.  
  
## <a name="race-conditions-in-constructors"></a>Конкуренция в конструкторах  
 В некоторых приложениях может быть возможно для доступа к членам класса, до их конструкторов класса полностью запуска других потоков. Изучите все конструкторы класса, чтобы убедиться в отсутствии проблем безопасности, не должно происходить, либо синхронизации потоков, при необходимости.  
  
## <a name="race-conditions-with-cached-objects"></a>Состояние гонки и кэшированные объекты  
 Код, который кэширует сведения о безопасности и управления доступом для кода использует [Assert](../../../docs/framework/misc/using-the-assert-method.md) операции может также стать уязвимым для конкуренции Если других частей класса не синхронизированы должным образом, как показано в следующем примере.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 Если есть другие пути к `DoOtherWork` может вызываться из другого потока с этим же объектом, ненадежный вызывающий объект может обойти требование.  
  
 Если код кэширует сведения о безопасности, убедитесь, просмотрите этой уязвимости.  
  
## <a name="race-conditions-in-finalizers"></a>Состояния гонки в методах завершения  
 В объекте, который ссылается на статический или неуправляемый ресурс, затем освобождает в его завершения может возникнуть состояние гонки. Если несколько объектов совместно используют ресурс, который обрабатывается в методе завершения класса, объекты должны синхронизировать все обращения к этому ресурсу.  
  
## <a name="see-also"></a>См. также  
 [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)
