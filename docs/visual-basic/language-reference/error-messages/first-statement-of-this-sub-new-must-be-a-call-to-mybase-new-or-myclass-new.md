---
title: "Первый оператор в это &#39; Конструктор Sub New &#39; должен быть вызов &#39; MyBase.New &#39; или &#39; MyClass.New &#39; (Нет доступного конструктора без параметров)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords: BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>Первый оператор в это &#39; Конструктор Sub New &#39; должен быть вызов &#39; MyBase.New &#39; или &#39; MyClass.New &#39; (Нет доступного конструктора без параметров)
Первый оператор данного «Sub New» должен быть вызов «MyBase.New» или «MyClass.New», так как базовый класс\<базовое имя > "из"\<derivedname > "не имеет доступного «Sub New», который может вызываться без аргументов.  
  
 В производном классе все конструкторы должны вызывать конструктор базового класса (`MyBase.New`). Если базовый класс имеет конструктор без параметров, доступных производным классам `MyBase.New` может вызываться автоматически. В противном случае конструктор базового класса должен вызываться с параметрами, и это не может быть сделано автоматически. В этом случае первый оператор всех конструкторов производного класса необходимо вызвать параметризованный конструктор базового класса, или вызов другого конструктора в производном классе, который делает вызов конструктора базового класса.  
  
 **Идентификатор ошибки:** BC30148  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Вызвать `MyBase.New` предоставляющий необходимые параметры, или другой конструктор, выполняющий подобный вызов.  
  
     Например, если базовый класс имеет конструктор, который объявлен как `Public Sub New(ByVal index as Integer)`, первый оператор в производном класса конструктор может быть `MyBase.New(100)`.  
  
## <a name="see-also"></a>См. также  
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
