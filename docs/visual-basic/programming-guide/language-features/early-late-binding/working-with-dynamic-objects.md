---
title: "Работа с динамическими объектами (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d1e1c4f7338daad0f1101f6e886eba6c37316b0e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a><span data-ttu-id="c7b40-102">Работа с динамическими объектами (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7b40-102">Working with Dynamic Objects (Visual Basic)</span></span>
<span data-ttu-id="c7b40-103">Динамические объекты предоставляют другой способ, отличного от `Object` тип позднего связывания объекта во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7b40-103">Dynamic objects provide another way, other than the `Object` type, to late bind to an object at run time.</span></span> <span data-ttu-id="c7b40-104">Динамический объект предоставляет элементы, такие как свойства и методы во время выполнения, используя динамический интерфейс, которые определены в <xref:System.Dynamic>имен.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="c7b40-104">A dynamic object exposes members such as properties and methods at run time by using dynamic interfaces that are defined in the <xref:System.Dynamic> namespace.</span></span> <span data-ttu-id="c7b40-105">Можно использовать классы в <xref:System.Dynamic>пространство имен для создания объектов, работающих со структурами данных, не соответствующими статическому типу или формату.</xref:System.Dynamic></span><span class="sxs-lookup"><span data-stu-id="c7b40-105">You can use the classes in the <xref:System.Dynamic> namespace to create objects that work with data structures that do not match a static type or format.</span></span> <span data-ttu-id="c7b40-106">Можно также использовать динамические объекты, определенные в динамических языках, таких как IronPython и IronRuby.</span><span class="sxs-lookup"><span data-stu-id="c7b40-106">You can also use the dynamic objects that are defined in dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="c7b40-107">Примеры, демонстрирующие способы создания динамических объектов или использовать динамического объекта, определенного на динамическом языке см. в разделе [Пошаговое руководство: создание с помощью динамических объектов и](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, или <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="c7b40-107">For examples that show how to create dynamic objects or use a dynamic object defined in a dynamic language, see [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, or <xref:System.Dynamic.ExpandoObject>.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c7b40-108">создает привязку к объектам среды выполнения динамических языков и динамических языков, таких как IronPython и IronRuby, используя <xref:System.Dynamic.IDynamicMetaObjectProvider>интерфейса.</xref:System.Dynamic.IDynamicMetaObjectProvider></span><span class="sxs-lookup"><span data-stu-id="c7b40-108"> binds to objects from the dynamic language runtime and dynamic languages such as IronPython and IronRuby by using the <xref:System.Dynamic.IDynamicMetaObjectProvider> interface.</span></span> <span data-ttu-id="c7b40-109">Примеры классов, реализующих `IDynamicMetaObjectProvider` интерфейс — <xref:System.Dynamic.DynamicObject>и <xref:System.Dynamic.ExpandoObject>классы.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="c7b40-109">Examples of classes that implement the `IDynamicMetaObjectProvider` interface are the <xref:System.Dynamic.DynamicObject> and <xref:System.Dynamic.ExpandoObject> classes.</span></span>  
  
 <span data-ttu-id="c7b40-110">Если объект, реализующий производится вызов с поздним связыванием `IDynamicMetaObjectProvider` интерфейс, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] привязывается к динамическому объекту с помощью этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c7b40-110">If a late-bound call is made to an object that implements the `IDynamicMetaObjectProvider` interface, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the dynamic object by using that interface.</span></span> <span data-ttu-id="c7b40-111">Если вызов с поздним связыванием объект, который не реализует `IDynamicMetaObjectProvider` интерфейс, или, если вызов `IDynamicMetaObjectProvider` интерфейс завершается ошибкой, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] привязывается к объекту с помощью возможностей позднего связывания [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c7b40-111">If a late-bound call is made to an object that does not implement the `IDynamicMetaObjectProvider` interface, or if the call to the `IDynamicMetaObjectProvider` interface fails, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] binds to the object by using the late-binding capabilities of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b40-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c7b40-112">See Also</span></span>  
 <span data-ttu-id="c7b40-113"><xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject></span><span class="sxs-lookup"><span data-stu-id="c7b40-113"><xref:System.Dynamic.DynamicObject></span></span>   
 <span data-ttu-id="c7b40-114"><xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject></span><span class="sxs-lookup"><span data-stu-id="c7b40-114"><xref:System.Dynamic.ExpandoObject></span></span>   
<span data-ttu-id="c7b40-115"> [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span><span class="sxs-lookup"><span data-stu-id="c7b40-115"> [Walkthrough: Creating and Using Dynamic Objects](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) </span></span>  
<span data-ttu-id="c7b40-116"> [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span><span class="sxs-lookup"><span data-stu-id="c7b40-116"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)</span></span>
