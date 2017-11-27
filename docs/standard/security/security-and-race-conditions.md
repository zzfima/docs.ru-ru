---
title: "Безопасность и конфликты"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c092113f670c5799d98dcb13c9c713bbd1a47fb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="fce5d-102">Безопасность и конфликты</span><span class="sxs-lookup"><span data-stu-id="fce5d-102">Security and Race Conditions</span></span>
<span data-ttu-id="fce5d-103">Другой областью проблемных является возможность бреши в гонки безопасности.</span><span class="sxs-lookup"><span data-stu-id="fce5d-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="fce5d-104">Существует несколько способов, в которых это может произойти.</span><span class="sxs-lookup"><span data-stu-id="fce5d-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="fce5d-105">Нижеследующие подразделы описывают некоторые основные ловушки, которые разработчик должен обойти.</span><span class="sxs-lookup"><span data-stu-id="fce5d-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="fce5d-106">Состояния гонки в методе Dispose</span><span class="sxs-lookup"><span data-stu-id="fce5d-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="fce5d-107">Если класс **Dispose** метод (Дополнительные сведения см. в разделе [мусора](../../../docs/standard/garbage-collection/index.md)) — не синхронизирован, существует возможность, код очистки в **Dispose** может выполняться более чем один раз, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fce5d-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="fce5d-108">Так как это **Dispose** реализации не синхронизирована, то возможна `Cleanup` будет вызвана сначала одним потоком, а затем второй поток перед `_myObj` задано значение **null**.</span><span class="sxs-lookup"><span data-stu-id="fce5d-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="fce5d-109">Является ли это угроза безопасности зависит от того, что происходит при `Cleanup` выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="fce5d-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="fce5d-110">Основная проблема, связанная с несинхронизированные **Dispose** реализациями относится к использованию дескрипторов ресурсов, таких как файлы.</span><span class="sxs-lookup"><span data-stu-id="fce5d-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="fce5d-111">Неверное удаление может привести неправильное дескриптора для использования, что часто приводит к уязвимости системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="fce5d-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="fce5d-112">Конкуренция в конструкторах</span><span class="sxs-lookup"><span data-stu-id="fce5d-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="fce5d-113">В некоторых приложениях может быть возможно для доступа к членам класса, до их конструкторов класса полностью запуска других потоков.</span><span class="sxs-lookup"><span data-stu-id="fce5d-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="fce5d-114">Изучите все конструкторы класса, чтобы убедиться в отсутствии проблем безопасности, не должно происходить, либо синхронизации потоков, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="fce5d-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="fce5d-115">Состояние гонки и кэшированные объекты</span><span class="sxs-lookup"><span data-stu-id="fce5d-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="fce5d-116">Код, который кэширует сведения о безопасности и управления доступом для кода использует [Assert](../../../docs/framework/misc/using-the-assert-method.md) операции может также стать уязвимым для конкуренции Если других частей класса не синхронизированы должным образом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fce5d-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="fce5d-117">Если есть другие пути к `DoOtherWork` может вызываться из другого потока с этим же объектом, ненадежный вызывающий объект может обойти требование.</span><span class="sxs-lookup"><span data-stu-id="fce5d-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="fce5d-118">Если код кэширует сведения о безопасности, убедитесь, просмотрите этой уязвимости.</span><span class="sxs-lookup"><span data-stu-id="fce5d-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="fce5d-119">Состояния гонки в методах завершения</span><span class="sxs-lookup"><span data-stu-id="fce5d-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="fce5d-120">В объекте, который ссылается на статический или неуправляемый ресурс, затем освобождает в его завершения может возникнуть состояние гонки.</span><span class="sxs-lookup"><span data-stu-id="fce5d-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="fce5d-121">Если несколько объектов совместно используют ресурс, который обрабатывается в методе завершения класса, объекты должны синхронизировать все обращения к этому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="fce5d-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce5d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="fce5d-122">See Also</span></span>  
 [<span data-ttu-id="fce5d-123">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="fce5d-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
