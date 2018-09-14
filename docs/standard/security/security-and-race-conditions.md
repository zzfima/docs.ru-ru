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
ms.openlocfilehash: 57ceaedc7c38ae70a0db5a7fd584a765a7474aff
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45593170"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="2329e-102">Безопасность и конфликты</span><span class="sxs-lookup"><span data-stu-id="2329e-102">Security and Race Conditions</span></span>
<span data-ttu-id="2329e-103">Еще одна группа проблемой является возможность бреши в гонки безопасности.</span><span class="sxs-lookup"><span data-stu-id="2329e-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="2329e-104">Существует несколько способов, в которых это может произойти.</span><span class="sxs-lookup"><span data-stu-id="2329e-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="2329e-105">Нижеследующие подразделы описывают некоторые основные ловушки, которые разработчик должен обойти.</span><span class="sxs-lookup"><span data-stu-id="2329e-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="2329e-106">Состояния гонки в методе Dispose</span><span class="sxs-lookup"><span data-stu-id="2329e-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="2329e-107">Если класс **Dispose** метод (Дополнительные сведения см. в разделе [сбора мусора](../../../docs/standard/garbage-collection/index.md)) является не синхронизирован, возможна ситуация, код очистки внутри **Dispose** могут выполняться более чем один раз, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2329e-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="2329e-108">Так как это **Dispose** реализации не синхронизированы, можно для `Cleanup` будет вызвана сначала одним потоком, а затем второй поток перед `_myObj` присваивается **null**.</span><span class="sxs-lookup"><span data-stu-id="2329e-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="2329e-109">Является ли это проблему безопасности зависит от того, что происходит, когда `Cleanup` выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="2329e-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="2329e-110">Основная проблема, связанная с несинхронизированных **Dispose** реализации включает использование дескрипторов ресурсов, таких как файлы.</span><span class="sxs-lookup"><span data-stu-id="2329e-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="2329e-111">Ненадлежащая утилизация может привести к неправильный дескриптор для использования, что часто приводит к уязвимости системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="2329e-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="2329e-112">Конкуренция в конструкторах</span><span class="sxs-lookup"><span data-stu-id="2329e-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="2329e-113">В некоторых приложениях может быть возможность для других потоков, для доступа к членам класса, прежде чем будут полностью выполнены конструкторов их класса.</span><span class="sxs-lookup"><span data-stu-id="2329e-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="2329e-114">Проанализируйте все конструкторы класса, чтобы убедиться в отсутствии проблем безопасности, если это должно произойти или синхронизации потоков, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2329e-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="2329e-115">Состояние гонки и кэшированные объекты</span><span class="sxs-lookup"><span data-stu-id="2329e-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="2329e-116">Код, который кэширует сведения о безопасности или использует безопасности доступа кода [Assert](../../../docs/framework/misc/using-the-assert-method.md) операции также может уязвимым для конкуренции при других частей класса не синхронизированы должным образом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2329e-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="2329e-117">Если есть другие пути к `DoOtherWork` , может быть вызван из другого потока с тем же объектом, ненадежный вызывающий объект может обойти требование.</span><span class="sxs-lookup"><span data-stu-id="2329e-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="2329e-118">Если кода кэширует сведения о безопасности, убедитесь, что вы просмотрели его за этой уязвимости.</span><span class="sxs-lookup"><span data-stu-id="2329e-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="2329e-119">Гонки в методах завершения</span><span class="sxs-lookup"><span data-stu-id="2329e-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="2329e-120">Конфликты могут также возникать в объекте, который ссылается на статический или неуправляемый ресурс, он затем освобождает его метод завершения.</span><span class="sxs-lookup"><span data-stu-id="2329e-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="2329e-121">Если несколько объектов, совместно используют ресурс, который обрабатывается в финализаторе класса, объекты должны синхронизировать все обращения к этому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="2329e-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2329e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2329e-122">See also</span></span>

- [<span data-ttu-id="2329e-123">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="2329e-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
