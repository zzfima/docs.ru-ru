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
ms.openlocfilehash: 8980122acdd069bc840aa09129483a1cb9a379fd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705877"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="a724e-102">Безопасность и конфликты</span><span class="sxs-lookup"><span data-stu-id="a724e-102">Security and Race Conditions</span></span>
<span data-ttu-id="a724e-103">Другой проблемой является возможность использования брешей в безопасности в условиях состязания.</span><span class="sxs-lookup"><span data-stu-id="a724e-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="a724e-104">Это может произойти несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="a724e-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="a724e-105">Подразделы, приведенные ниже, описывают некоторые основные ошибки, которые разработчику следует избегать.</span><span class="sxs-lookup"><span data-stu-id="a724e-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="a724e-106">Состояния гонки в методе Dispose</span><span class="sxs-lookup"><span data-stu-id="a724e-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="a724e-107">Если метод **Dispose** класса (Дополнительные сведения см. в разделе [сборка мусора](../../../docs/standard/garbage-collection/index.md)) не синхронизирован, возможно, что код очистки внутри **Dispose** может быть запущен более одного раза, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a724e-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="a724e-108">Поскольку эта реализация **Dispose** не синхронизирована, `Cleanup` может быть вызвана первым потоком, а затем вторым потоком до того, как `_myObj` задается **значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="a724e-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="a724e-109">Является ли это нарушением безопасности, зависит от того, что происходит при выполнении кода `Cleanup`.</span><span class="sxs-lookup"><span data-stu-id="a724e-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="a724e-110">Основной проблемой с несинхронизированными реализациями **Dispose** является использование таких дескрипторов ресурсов, как файлы.</span><span class="sxs-lookup"><span data-stu-id="a724e-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="a724e-111">Неправильное удаление может привести к тому, что не будет использован некорректный маркер, что часто приводит к уязвимостям безопасности.</span><span class="sxs-lookup"><span data-stu-id="a724e-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="a724e-112">Состояния гонки в конструкторах</span><span class="sxs-lookup"><span data-stu-id="a724e-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="a724e-113">В некоторых приложениях другие потоки могут обращаться к членам класса, прежде чем их конструкторы класса будут полностью запущены.</span><span class="sxs-lookup"><span data-stu-id="a724e-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="a724e-114">Следует проверить все конструкторы классов, чтобы убедиться в отсутствии проблем безопасности, если это необходимо, или синхронизировать потоки при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a724e-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="a724e-115">Состояния гонки с кэшированными объектами</span><span class="sxs-lookup"><span data-stu-id="a724e-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="a724e-116">Код, который кэширует сведения о безопасности или использует операцию [утверждения](../../../docs/framework/misc/using-the-assert-method.md) управления доступом для кода, может также быть уязвимым для состояний гонки, если другие части класса не синхронизированы должным образом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a724e-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="a724e-117">Если есть другие пути к `DoOtherWork`, которые могут быть вызваны из другого потока с тем же объектом, недоверенный вызывающий объект может потребовать последующего запроса.</span><span class="sxs-lookup"><span data-stu-id="a724e-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="a724e-118">Если ваш код кэширует сведения о безопасности, обязательно ознакомьтесь с этой уязвимостью.</span><span class="sxs-lookup"><span data-stu-id="a724e-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="a724e-119">Состояния гонки в методах завершения</span><span class="sxs-lookup"><span data-stu-id="a724e-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="a724e-120">Состояния гонки могут также возникать в объекте, который ссылается на статический или неуправляемый ресурс, который затем освобождается в методе завершения.</span><span class="sxs-lookup"><span data-stu-id="a724e-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="a724e-121">Если несколько объектов совместно используют ресурс, который управляется в методе завершения класса, объекты должны синхронизировать весь доступ к этому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="a724e-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a724e-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="a724e-122">See also</span></span>

- [<span data-ttu-id="a724e-123">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="a724e-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
