---
title: Безопасность и конфликты
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
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
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186782"
---
# <a name="security-and-race-conditions"></a>Безопасность и конфликты
Еще одной областью, вызывающей озабоченность, является потенциал для возникновения дыр в безопасности, используемых в условиях расы. Есть несколько способов, в которых это может произойти. Подтопические темы, которые следуют, излагают некоторые из основных подводных камней, которых разработчик должен избегать.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Условия гонки в методе утилизации  
 Если метод **dispose** -15-го класса (для получения дополнительной информации см. [Сбор мусора)](../../../docs/standard/garbage-collection/index.md)не синхронизирован, возможно, что код очистки внутри **Dispose** может быть запущен более одного раза, как показано в следующем примере.  
  
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
    if (myObj != null)
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 Поскольку эта реализация **Dispose** не синхронизирована, `Cleanup` можно вызвать сначала один поток, `_myObj` а затем второй поток, прежде чем будет сведен на **нет.** Является ли это проблемой безопасности, `Cleanup` зависит от того, что происходит при запуске кода. Основная проблема с несинхронизированными реализациями **Dispose** связана с использованием ручек ресурсов, таких как файлы. Неправильное удаление может привести к неправильному использованию ручки, что часто приводит к уязвимостям в системе безопасности.  
  
## <a name="race-conditions-in-constructors"></a>Условия гонки в конструкторах  
 В некоторых приложениях может быть возможно, чтобы другие потоки имели доступ к членам класса до полного запуска их конструкторов классов. Следует просмотреть все конструкторы классов, чтобы убедиться, что в случае необходимости не возникает проблем с безопасностью, или при необходимости синхронизировать потоки.  
  
## <a name="race-conditions-with-cached-objects"></a>Условия гонки с кэшированными объектами  
 Код, который кэширует информацию о безопасности или использует операцию безопасности доступа к коду [Assert,](../../../docs/framework/misc/using-the-assert-method.md) также может быть уязвим для условий гонки, если другие части класса не синхронизированы надлежащим образом, как показано в следующем примере.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
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
    if (SomeDemandPasses())
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()
{  
    if (fCallersOK)
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
  
 Если есть другие `DoOtherWork` пути к этому можно вызвать из другого потока с тем же объектом, недоверчивый абонент может проскользнуть мимо спроса.  
  
 Если код кэширует информацию о безопасности, убедитесь, что вы просмотрите ее для этой уязвимости.  
  
## <a name="race-conditions-in-finalizers"></a>Условия гонки в Finalizers  
 Условия гонки могут также возникать в объекте, который ссылается на статический или неуправляемый ресурс, который он затем освобождает в своем finalizer. Если несколько объектов разделяют ресурс, которым манипулируют в финализаторе класса, объекты должны синхронизировать весь доступ к этому ресурсу.  
  
## <a name="see-also"></a>См. также раздел

- [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)
