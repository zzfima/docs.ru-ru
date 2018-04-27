---
title: Работа с динамическими объектами (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f00c57107da5e6ea428e14964d8fa4a870bc96c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="e81a9-102">Работа с динамическими объектами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e81a9-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="e81a9-103">Динамические объекты предоставляют другой способ, отличный от `Object` тип позднего связывания объекта во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e81a9-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="e81a9-104">Динамический объект предоставляет элементы, такие как свойства и методы во время выполнения с помощью динамического интерфейсы, которые определены в <xref:System.Dynamic> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="e81a9-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="e81a9-105">Можно использовать классы в <xref:System.Dynamic> пространства имен для создания объектов, работающих со структурами данных, которые не соответствуют статический тип или формат.</span><span class="sxs-lookup"><span data-stu-id="e81a9-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="e81a9-106">Можно также использовать динамические объекты, которые определены в динамических языках, таких как IronPython и IronRuby.</span><span class="sxs-lookup"><span data-stu-id="e81a9-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="e81a9-107">Примеры, демонстрирующие способы создания динамических объектов или использовать динамический объект, определенный в динамической среды см. в разделе [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, или <xref:System.Dynamic.ExpandoObject>.</span><span class="sxs-lookup"><span data-stu-id="e81a9-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 <span data-ttu-id="e81a9-108">Visual Basic выполняет привязку к объектам из динамической среды выполнения и динамических языках, таких как IronPython и IronRuby, используя <xref:System.Dynamic.IDynamicMetaObjectProvider> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e81a9-108">Visual Basic binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="e81a9-109">Примеры классов, реализующих `IDynamicMetaObjectProvider` интерфейс — <xref:System.Dynamic.DynamicObject> и <xref:System.Dynamic.ExpandoObject> классы.</span><span class="sxs-lookup"><span data-stu-id="e81a9-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="e81a9-110">Если вызов с поздним связыванием устанавливается с объектом, реализующим `IDynamicMetaObjectProvider` интерфейс Visual Basic привязывается к динамическому объекту с помощью этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e81a9-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, Visual Basic binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="e81a9-111">Если выполняется позднего связывания вызов в объект, который не реализует `IDynamicMetaObjectProvider` интерфейса, или, если вызов `IDynamicMetaObjectProvider` интерфейса не удастся, Visual Basic выполняет привязку к объекту с помощью возможностей позднего связывания среды выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e81a9-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, Visual Basic binds to the object by using the late-binding capabilities of the Visual Basic runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81a9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e81a9-112">See Also</span></span>  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [<span data-ttu-id="e81a9-113">Пошаговое руководство. Создание и использование динамических объектов</span><span class="sxs-lookup"><span data-stu-id="e81a9-113">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [<span data-ttu-id="e81a9-114">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="e81a9-114">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
