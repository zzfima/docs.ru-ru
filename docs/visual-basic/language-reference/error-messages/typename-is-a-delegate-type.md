---
title: '&#39;&lt;TypeName&gt; &#39; является типом делегата'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 6676328d0c1ea459f5934b5f9e2cb66580adad40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737206"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39;&lt;TypeName&gt; &#39; является типом делегата
"\<typename >" является типом делегата. Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов. Часто выражение AddressOf может использоваться вместо конструкции делегата.  
  
 Объект `New` создании экземпляра класса делегата передает список недопустимый аргумент конструктора делегата.  
  
 Можно указать только один `AddressOf` выражения при создании нового экземпляра делегата.  
  
 Эта ошибка может возникнуть, если не передать аргументы конструктора делегата, если можно передать несколько аргументов, или если передать один аргумент, не является допустимым `AddressOf` выражение.  
  
 **Идентификатор ошибки:** BC32008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Использовать единую `AddressOf` выражение в списке аргументов для класса делегата в `New` предложение.  
  
## <a name="see-also"></a>См. также
- [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)
- [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Практическое руководство. Вызов метода делегата](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
