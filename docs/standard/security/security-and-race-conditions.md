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
ms.openlocfilehash: 3e613ad4823254a6bed43cb95294e6b8d3674b6d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881753"
---
# <a name="security-and-race-conditions"></a>Безопасность и конфликты
Еще одна группа проблемой является возможность бреши в гонки безопасности. Существует несколько способов, в которых это может произойти. Нижеследующие подразделы описывают некоторые основные ловушки, которые разработчик должен обойти.  
  
## <a name="race-conditions-in-the-dispose-method"></a>Состояния гонки в методе Dispose  
 Если класс **Dispose** метод (Дополнительные сведения см. в разделе [сбора мусора](../../../docs/standard/garbage-collection/index.md)) является не синхронизирован, возможна ситуация, код очистки внутри **Dispose** могут выполняться более чем один раз, как показано в следующем примере.  
  
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
  
 Так как это **Dispose** реализации не синхронизированы, можно для `Cleanup` будет вызвана сначала одним потоком, а затем второй поток перед `_myObj` присваивается **null**. Является ли это проблему безопасности зависит от того, что происходит, когда `Cleanup` выполнении кода. Основная проблема, связанная с несинхронизированных **Dispose** реализации включает использование дескрипторов ресурсов, таких как файлы. Ненадлежащая утилизация может привести к неправильный дескриптор для использования, что часто приводит к уязвимости системы безопасности.  
  
## <a name="race-conditions-in-constructors"></a>Конкуренция в конструкторах  
 В некоторых приложениях может быть возможность для других потоков, для доступа к членам класса, прежде чем будут полностью выполнены конструкторов их класса. Проанализируйте все конструкторы класса, чтобы убедиться в отсутствии проблем безопасности, если это должно произойти или синхронизации потоков, при необходимости.  
  
## <a name="race-conditions-with-cached-objects"></a>Состояние гонки и кэшированные объекты  
 Код, который кэширует сведения о безопасности или использует безопасности доступа кода [Assert](../../../docs/framework/misc/using-the-assert-method.md) операции также может уязвимым для конкуренции при других частей класса не синхронизированы должным образом, как показано в следующем примере.  
  
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
  
 Если есть другие пути к `DoOtherWork` , может быть вызван из другого потока с тем же объектом, ненадежный вызывающий объект может обойти требование.  
  
 Если кода кэширует сведения о безопасности, убедитесь, что вы просмотрели его за этой уязвимости.  
  
## <a name="race-conditions-in-finalizers"></a>Гонки в методах завершения  
 Конфликты могут также возникать в объекте, который ссылается на статический или неуправляемый ресурс, он затем освобождает его метод завершения. Если несколько объектов, совместно используют ресурс, который обрабатывается в финализаторе класса, объекты должны синхронизировать все обращения к этому ресурсу.  
  
## <a name="see-also"></a>См. также

- [Правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md)
