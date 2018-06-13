---
title: '&#39;&lt;TypeName&gt; &#39; является типом делегата'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595652"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39;&lt;TypeName&gt; &#39; является типом делегата
"\<typename >" является типом делегата. Конструкция делегата позволяет использовать только одно выражение AddressOf как список аргументов. Часто выражение AddressOf может использоваться вместо конструкции делегата.  
  
 Объект `New` создании экземпляра класса делегата передает недопустимый список аргументов для конструктора делегата.  
  
 Можно задать только одно `AddressOf` выражения при создании нового экземпляра делегата.  
  
 Эта ошибка может возникнуть, если не передать аргументы конструктора делегата, если передать несколько аргументов, или если передается один аргумент, не является допустимым `AddressOf` выражение.  
  
 **Идентификатор ошибки:** BC32008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Использовать отдельный `AddressOf` выражение в списке аргументов для класса делегата в `New` предложения.  
  
## <a name="see-also"></a>См. также  
 [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Практическое руководство. Вызов метода делегата](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
