---
title: "&quot;&lt;typename&gt;&quot; является типом делегата | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
dev_langs:
- VB
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3d6cc283f7e9815eb9b723a450731998f14b3424
ms.lasthandoff: 03/13/2017

---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>"&lt;typename&gt;" является типом делегата
"\<typename настроек" является типом делегата. Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов. Часто выражение AddressOf может использоваться вместо конструкции делегата.  
  
 A `New` создании экземпляра класса делегата передает недопустимый список аргументов в конструктор делегата.  
  
 Можно указать только один `AddressOf` выражение при создании нового экземпляра делегата.  
  
 Эта ошибка может произойти, если не передать аргументы конструктора делегата, если передать несколько аргументов, или если передается один аргумент, не является допустимым `AddressOf` выражение.  
  
 **Идентификатор ошибки:** BC32008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Использовать единую `AddressOf` выражение в списке аргументов для класса делегата в `New` предложения.  
  
## <a name="see-also"></a>См. также  
 [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)   
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Практическое руководство. Вызов метода делегата](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
