---
title: Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: d29d7609f8f3f38eadda9a9c763f3ba8e6b99e61
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278542"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a>Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров)
Первый оператор в «Sub New» должен быть вызовом «MyBase.New» или «MyClass.New», так как базовый класс\<basename > "из"\<derivedname > "не имеет доступного «Sub New», который может быть вызван без аргументов.  
  
 В производном классе, каждый конструктор должен вызвать конструктор базового класса (`MyBase.New`). Если базовый класс имеет конструктор без параметров, доступных производным классам `MyBase.New` может вызываться автоматически. В противном случае необходимо вызвать конструктор базового класса с параметрами, и это не может быть сделано автоматически. В этом случае первый оператор в конструктор каждого производного класса необходимо вызвать параметризованный конструктор базового класса, или вызвать другой конструктор в производном классе, который делает вызов конструктора базового класса.  
  
 **Идентификатор ошибки:** BC30148  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Вызовите `MyBase.New` предоставляющий необходимые параметры, или другой конструктор, выполняющий подобный вызов.  
  
     Например, если базовый класс имеет конструктор, который объявляется как `Public Sub New(ByVal index as Integer)`, первый оператор в производный конструктор класса может быть `MyBase.New(100)`.  
  
## <a name="see-also"></a>См. также
- [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
