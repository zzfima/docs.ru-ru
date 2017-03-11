---
title: "Первым оператором в этой процедуре Sub New должен быть явный вызов MyBase.New или MyClass.New, так как &lt;имяКонструктора&gt; в базовом классе &lt;имяБазовогоКласса&gt; класса &lt;имяПроизводногоКласса&gt; отмечен как устаревший: &lt;сообщениеОбОшибке&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30920"
  - "bc30920"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30920"
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Первым оператором в этой процедуре Sub New должен быть явный вызов MyBase.New или MyClass.New, так как &lt;имяКонструктора&gt; в базовом классе &lt;имяБазовогоКласса&gt; класса &lt;имяПроизводногоКласса&gt; отмечен как устаревший: &lt;сообщениеОбОшибке&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Конструктор класса не вызывает явно конструктор базового класса, а неявный конструктор базового класса помечен атрибутом <xref:System.ObsoleteAttribute> и директивой, которая требует считать это ошибкой.  
  
 Если конструктор производного класса не вызывает конструктор базового класса, то [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] пытается сформировать неявный вызов конструктора базового класса без параметров.  Если в базовом классе нет доступного конструктора, который можно вызывать без аргументов, то [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] не удается создать неявный вызов.  В этом случае необходимый конструктор помечается атрибутом <xref:System.ObsoleteAttribute>, поэтому [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] не может вызвать его.  
  
 С помощью атрибута <xref:System.ObsoleteAttribute> можно пометить любой элемент программирования как более не используемый.  После этого можно задать для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута значение `True` или `False`.  Если задано значение `True`, компилятор рассматривает попытку использования элемента как ошибку.  Если задать значение `False` или оставить используемое по умолчанию значение `False`, то при попытке использовать элемент компилятор выдает предупреждение.  
  
 **Идентификатор ошибки:** BC30920  
  
### Чтобы исправить эту ошибку  
  
1.  Просмотрите сообщение об ошибке, заключенное в кавычки, и выполните необходимые действия.  
  
2.  Сделайте вызов `MyBase.New()` или `MyClass.New()` первым оператором в производном классе `Sub New`.  
  
## См. также  
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)