---
title: "Работа с динамическими объектами (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "динамические объекты [Visual Basic]"
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Работа с динамическими объектами (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Динамические объекты предоставляют другой способ, отличный от типа `Object`, позднего связывания с объектом во время выполнения.  Динамический объект предоставляет элементы, такие как свойства и методы, во время выполнения, используя динамический интерфейс, который определен в пространстве имен <xref:System.Dynamic>.  В пространстве имен <xref:System.Dynamic> есть возможность использования классов для создания объектов, работающих со структурами данных, не соответствующими статическому типу или формату.  Также можно использовать динамические объекты, определенные в динамических языках, таких как IronPython и IronRuby.  Например, для создания динамического объекта, определенного на динамическом языке, см. [Пошаговое руководство. Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> или <xref:System.Dynamic.ExpandoObject>.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает привязку к объектам среды выполнения динамических языков и динамических языков, таких как IronPythonи и IronRuby, используя интерфейс <xref:System.Dynamic.IDynamicMetaObjectProvider>.  Примерами классов, реализующих интерфейс `IDynamicMetaObjectProvider` являются <xref:System.Dynamic.DynamicObject> и <xref:System.Dynamic.ExpandoObject>.  
  
 Если выполняется вызов с поздним связыванием в отношении объекта, который реализует интерфейс `IDynamicMetaObjectProvider`, то [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает привязку к динамическому объекту с помощью этого интерфейса.  Если выполнен вызов с поздним связыванием в отношении объекта, который не реализует интерфейс `IDynamicMetaObjectProvider`, либо произошел сбой вызова интерфейса `IDynamicMetaObjectProvider`, то [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] создает привязку к объекту посредством возможностей позднего связывания среды выполнения [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## См. также  
 <xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject>   
 [Пошаговое руководство. Создание и использование динамических объектов](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)