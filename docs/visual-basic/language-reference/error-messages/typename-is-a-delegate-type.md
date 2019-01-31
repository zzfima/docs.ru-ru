---
title: <typename> является типом делегата
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4278ea0fc6a8dc2c6a90b720d2da70b1c26f2a17
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283456"
---
# <a name="typename-is-a-delegate-type"></a>"\<typename >" является типом делегата
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
