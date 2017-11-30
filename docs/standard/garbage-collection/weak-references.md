---
title: "Слабые ссылки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a><span data-ttu-id="a905b-102">Слабые ссылки</span><span class="sxs-lookup"><span data-stu-id="a905b-102">Weak References</span></span>
<span data-ttu-id="a905b-103">Сборщик мусора не может собрать объект, используемый приложением, пока код приложения взаимодействует с этим объектом.</span><span class="sxs-lookup"><span data-stu-id="a905b-103">The garbage collector cannot collect an object in use by an application while the application's code can reach that object.</span></span> <span data-ttu-id="a905b-104">Говорят, что приложение имеет строгую ссылку на объект.</span><span class="sxs-lookup"><span data-stu-id="a905b-104">The application is said to have a strong reference to the object.</span></span>  
  
 <span data-ttu-id="a905b-105">Слабая ссылка дает сборщику мусора возможность удалить объект, но в то же время обеспечивает приложению доступ к этому объекту.</span><span class="sxs-lookup"><span data-stu-id="a905b-105">A weak reference permits the garbage collector to collect the object while still allowing the application to access the object.</span></span> <span data-ttu-id="a905b-106">Слабая ссылка допустима только в течение неопределенного количества времени до сборки объекта при отсутствии строгих ссылок.</span><span class="sxs-lookup"><span data-stu-id="a905b-106">A weak reference is valid only during the indeterminate amount of time until the object is collected when no strong references exist.</span></span> <span data-ttu-id="a905b-107">При использовании слабой ссылки приложение все еще может получить строгую ссылку в объекте, что предотвратит удаление последнего.</span><span class="sxs-lookup"><span data-stu-id="a905b-107">When you use a weak reference, the application can still obtain a strong reference to the object, which prevents it from being collected.</span></span> <span data-ttu-id="a905b-108">Однако всегда существует вероятность удаления объекта сборщиком мусора до повторного создания строгой ссылки.</span><span class="sxs-lookup"><span data-stu-id="a905b-108">However, there is always the risk that the garbage collector will get to the object first before a strong reference is reestablished.</span></span>  
  
 <span data-ttu-id="a905b-109">Слабые ссылки полезны для объектов, которые используют большой объем памяти, но могут быть созданы повторно без особых усилий, если они были удалены сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="a905b-109">Weak references are useful for objects that use a lot of memory, but can be recreated easily if they are reclaimed by garbage collection.</span></span>  
  
 <span data-ttu-id="a905b-110">Предположим, что представление в виде дерева в приложении Windows Forms отображает иерархическую структуру различных параметров для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a905b-110">Suppose a tree view in a Windows Forms application displays a complex hierarchical choice of options to the user.</span></span> <span data-ttu-id="a905b-111">Если базовые данные большие по объему, хранение этого дерева в памяти является неэффективным, особенно если пользователь делает в этом приложении что-либо еще.</span><span class="sxs-lookup"><span data-stu-id="a905b-111">If the underlying data is large, keeping the tree in memory is inefficient when the user is involved with something else in the application.</span></span>  
  
 <span data-ttu-id="a905b-112">Если пользователь переключается на другую часть приложения, можно использовать <xref:System.WeakReference> класс для создания слабой ссылки в дерево и удалить все строгие ссылки.</span><span class="sxs-lookup"><span data-stu-id="a905b-112">When the user switches away to another part of the application, you can use the <xref:System.WeakReference> class to create a weak reference to the tree and destroy all strong references.</span></span> <span data-ttu-id="a905b-113">Когда пользователь переключится обратно к этому дереву, приложение попытается получить строгую ссылку на дерево и, при успешном выполнении этой операции, избежать повторного создания дерева.</span><span class="sxs-lookup"><span data-stu-id="a905b-113">When the user switches back to the tree, the application attempts to obtain a strong reference to the tree and, if successful, avoids reconstructing the tree.</span></span>  
  
 <span data-ttu-id="a905b-114">Чтобы установить гибкую ссылку на объект, следует создать <xref:System.WeakReference> отслеживаться с помощью экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="a905b-114">To establish a weak reference with an object, you create a <xref:System.WeakReference> using the instance of the object to be tracked.</span></span> <span data-ttu-id="a905b-115">Затем следует присвоить свойству <xref:System.WeakReference.Target%2A> этот объект и задать значение `null` для исходной ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="a905b-115">You then set the <xref:System.WeakReference.Target%2A> property to that object and set the original reference to the object to `null`.</span></span> <span data-ttu-id="a905b-116">Пример кода см. в разделе <xref:System.WeakReference> в библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="a905b-116">For a code example, see <xref:System.WeakReference> in the class library.</span></span>  
  
## <a name="short-and-long-weak-references"></a><span data-ttu-id="a905b-117">Краткие и длинные слабые ссылки</span><span class="sxs-lookup"><span data-stu-id="a905b-117">Short and Long Weak References</span></span>  
 <span data-ttu-id="a905b-118">Можно создать краткую слабую ссылку или длинную слабую ссылку:</span><span class="sxs-lookup"><span data-stu-id="a905b-118">You can create a short weak reference or a long weak reference:</span></span>  
  
-   <span data-ttu-id="a905b-119">Short</span><span class="sxs-lookup"><span data-stu-id="a905b-119">Short</span></span>  
  
     <span data-ttu-id="a905b-120">Назначением краткой ссылки становится `null`, если объект удален сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="a905b-120">The target of a short weak reference becomes `null` when the object is reclaimed by garbage collection.</span></span> <span data-ttu-id="a905b-121">Сама по себе слабая ссылка является управляемым объектом и подлежит сборке мусора, как и любые другие управляемые объекты.</span><span class="sxs-lookup"><span data-stu-id="a905b-121">The weak reference is itself a managed object, and is subject to garbage collection just like any other managed object.</span></span>  <span data-ttu-id="a905b-122">Краткая слабая ссылка является конструктором по умолчанию для <xref:System.WeakReference>.</span><span class="sxs-lookup"><span data-stu-id="a905b-122">A short weak reference is the default constructor for <xref:System.WeakReference>.</span></span>  
  
-   <span data-ttu-id="a905b-123">Long</span><span class="sxs-lookup"><span data-stu-id="a905b-123">Long</span></span>  
  
     <span data-ttu-id="a905b-124">Длинная слабая ссылка сохраняется после создания объекта <xref:System.Object.Finalize%2A> был вызван метод.</span><span class="sxs-lookup"><span data-stu-id="a905b-124">A long weak reference is retained after the object's <xref:System.Object.Finalize%2A> method has been called.</span></span> <span data-ttu-id="a905b-125">Это позволяет повторно создавать объект, однако состояние объекта остается непредсказуемым.</span><span class="sxs-lookup"><span data-stu-id="a905b-125">This allows the object to be recreated, but the state of the object remains unpredictable.</span></span> <span data-ttu-id="a905b-126">Чтобы использовать длинные ссылку, укажите `true` в <xref:System.WeakReference> конструктора.</span><span class="sxs-lookup"><span data-stu-id="a905b-126">To use a long reference, specify `true` in the <xref:System.WeakReference> constructor.</span></span>  
  
     <span data-ttu-id="a905b-127">Если тип объекта не имеет <xref:System.Object.Finalize%2A> применяется метод, функциональность краткой слабой ссылки и слабая ссылка является допустимым только до целевой сборки, которой может произойти в любое время после завершения выполнения.</span><span class="sxs-lookup"><span data-stu-id="a905b-127">If the object's type does not have a <xref:System.Object.Finalize%2A> method, the short weak reference functionality applies and the weak reference is valid only until the target is collected, which can occur anytime after the finalizer is run.</span></span>  
  
 <span data-ttu-id="a905b-128">Чтобы установить строгую ссылку и повторно использовать объект, приведите <xref:System.WeakReference.Target%2A> свойство <xref:System.WeakReference> типу объекта.</span><span class="sxs-lookup"><span data-stu-id="a905b-128">To establish a strong reference and use the object again, cast the <xref:System.WeakReference.Target%2A> property of a <xref:System.WeakReference> to the type of the object.</span></span> <span data-ttu-id="a905b-129">Если <xref:System.WeakReference.Target%2A> возвращает `null`, объект был собранных; в противном случае, можно продолжать использовать объект, так как приложение восстановило строгую ссылку.</span><span class="sxs-lookup"><span data-stu-id="a905b-129">If the <xref:System.WeakReference.Target%2A> property returns `null`, the object was collected; otherwise, you can continue to use the object because the application has regained a strong reference to it.</span></span>  
  
## <a name="guidelines-for-using-weak-references"></a><span data-ttu-id="a905b-130">Правила использования слабых ссылок</span><span class="sxs-lookup"><span data-stu-id="a905b-130">Guidelines for Using Weak References</span></span>  
 <span data-ttu-id="a905b-131">Используйте длинные слабые ссылки только при необходимости, так как состояние объекта после выполнения завершения становится непредсказуемым.</span><span class="sxs-lookup"><span data-stu-id="a905b-131">Use long weak references only when necessary as the state of the object is unpredictable after finalization.</span></span>  
  
 <span data-ttu-id="a905b-132">Избегайте использования слабых ссылок на небольшие объекты, потому что сам указатель может быть таким же по объему или даже больше.</span><span class="sxs-lookup"><span data-stu-id="a905b-132">Avoid using weak references to small objects because the pointer itself may be as large or larger.</span></span>  
  
 <span data-ttu-id="a905b-133">Избегайте использования слабых ссылок в качестве автоматического решения проблем, связанных с управлением памятью.</span><span class="sxs-lookup"><span data-stu-id="a905b-133">Avoid using weak references as an automatic solution to memory management problems.</span></span> <span data-ttu-id="a905b-134">Вместо этого разработайте эффективную политику кэширования для обработки объектов приложения.</span><span class="sxs-lookup"><span data-stu-id="a905b-134">Instead, develop an effective caching policy for handling your application's objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a905b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a905b-135">See Also</span></span>  
 [<span data-ttu-id="a905b-136">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="a905b-136">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
