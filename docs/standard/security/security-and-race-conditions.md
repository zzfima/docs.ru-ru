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
# <a name="security-and-race-conditions"></a><span data-ttu-id="c2ae3-102">Безопасность и конфликты</span><span class="sxs-lookup"><span data-stu-id="c2ae3-102">Security and Race Conditions</span></span>
<span data-ttu-id="c2ae3-103">Еще одной областью, вызывающей озабоченность, является потенциал для возникновения дыр в безопасности, используемых в условиях расы.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="c2ae3-104">Есть несколько способов, в которых это может произойти.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="c2ae3-105">Подтопические темы, которые следуют, излагают некоторые из основных подводных камней, которых разработчик должен избегать.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="c2ae3-106">Условия гонки в методе утилизации</span><span class="sxs-lookup"><span data-stu-id="c2ae3-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="c2ae3-107">Если метод **dispose** -15-го класса (для получения дополнительной информации см. [Сбор мусора)](../../../docs/standard/garbage-collection/index.md)не синхронизирован, возможно, что код очистки внутри **Dispose** может быть запущен более одного раза, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="c2ae3-108">Поскольку эта реализация **Dispose** не синхронизирована, `Cleanup` можно вызвать сначала один поток, `_myObj` а затем второй поток, прежде чем будет сведен на **нет.**</span><span class="sxs-lookup"><span data-stu-id="c2ae3-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="c2ae3-109">Является ли это проблемой безопасности, `Cleanup` зависит от того, что происходит при запуске кода.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="c2ae3-110">Основная проблема с несинхронизированными реализациями **Dispose** связана с использованием ручек ресурсов, таких как файлы.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="c2ae3-111">Неправильное удаление может привести к неправильному использованию ручки, что часто приводит к уязвимостям в системе безопасности.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="c2ae3-112">Условия гонки в конструкторах</span><span class="sxs-lookup"><span data-stu-id="c2ae3-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="c2ae3-113">В некоторых приложениях может быть возможно, чтобы другие потоки имели доступ к членам класса до полного запуска их конструкторов классов.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="c2ae3-114">Следует просмотреть все конструкторы классов, чтобы убедиться, что в случае необходимости не возникает проблем с безопасностью, или при необходимости синхронизировать потоки.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="c2ae3-115">Условия гонки с кэшированными объектами</span><span class="sxs-lookup"><span data-stu-id="c2ae3-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="c2ae3-116">Код, который кэширует информацию о безопасности или использует операцию безопасности доступа к коду [Assert,](../../../docs/framework/misc/using-the-assert-method.md) также может быть уязвим для условий гонки, если другие части класса не синхронизированы надлежащим образом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="c2ae3-117">Если есть другие `DoOtherWork` пути к этому можно вызвать из другого потока с тем же объектом, недоверчивый абонент может проскользнуть мимо спроса.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="c2ae3-118">Если код кэширует информацию о безопасности, убедитесь, что вы просмотрите ее для этой уязвимости.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="c2ae3-119">Условия гонки в Finalizers</span><span class="sxs-lookup"><span data-stu-id="c2ae3-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="c2ae3-120">Условия гонки могут также возникать в объекте, который ссылается на статический или неуправляемый ресурс, который он затем освобождает в своем finalizer.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="c2ae3-121">Если несколько объектов разделяют ресурс, которым манипулируют в финализаторе класса, объекты должны синхронизировать весь доступ к этому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c2ae3-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ae3-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c2ae3-122">See also</span></span>

- [<span data-ttu-id="c2ae3-123">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="c2ae3-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
