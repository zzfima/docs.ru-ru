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
# <a name="working-with-dynamic-objects-visual-basic"></a>Работа с динамическими объектами (Visual Basic)
Динамические объекты предоставляют другой способ, отличный от `Object` тип позднего связывания объекта во время выполнения. Динамический объект предоставляет элементы, такие как свойства и методы во время выполнения с помощью динамического интерфейсы, которые определены в <xref:System.Dynamic> пространства имен. Можно использовать классы в <xref:System.Dynamic> пространства имен для создания объектов, работающих со структурами данных, которые не соответствуют статический тип или формат. Можно также использовать динамические объекты, которые определены в динамических языках, таких как IronPython и IronRuby. Примеры, демонстрирующие способы создания динамических объектов или использовать динамический объект, определенный в динамической среды см. в разделе [Пошаговое руководство: Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, или <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic выполняет привязку к объектам из динамической среды выполнения и динамических языках, таких как IronPython и IronRuby, используя <xref:System.Dynamic.IDynamicMetaObjectProvider> интерфейса. Примеры классов, реализующих `IDynamicMetaObjectProvider` интерфейс — <xref:System.Dynamic.DynamicObject> и <xref:System.Dynamic.ExpandoObject> классы.  
  
 Если вызов с поздним связыванием устанавливается с объектом, реализующим `IDynamicMetaObjectProvider` интерфейс Visual Basic привязывается к динамическому объекту с помощью этого интерфейса. Если выполняется позднего связывания вызов в объект, который не реализует `IDynamicMetaObjectProvider` интерфейса, или, если вызов `IDynamicMetaObjectProvider` интерфейса не удастся, Visual Basic выполняет привязку к объекту с помощью возможностей позднего связывания среды выполнения Visual Basic.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [Пошаговое руководство. Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
