---
title: Невозможно обратиться к полю <name>, так как оно является членом поля с типизированным значением <name> класса <classname>, базовым классом которого является System.MarshalByRefObject
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: aac190119ced74496c4dd012d200fca6d895ff28
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826773"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a>Не может ссылаться на "\<имя >", так как он является членом поля с типизированным значением "\<имя >" класса\<имя_класса > "которого является «System.MarshalByRefObject» как базовый класс
`System.MarshalByRefObject` Класс позволяет приложения, поддерживающие удаленный доступ к объектам через границы домена приложения. Типы должны быть наследниками `MarshalByRejectObject` класса при использовании типа через границы домена приложения. Состояние объекта не должны копироваться, так как члены объекта не могут использоваться за пределами домена приложения, в котором они были созданы.  
  
 **Идентификатор ошибки:** BC30310  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверяет ссылку, чтобы убедиться в том, что член является допустимым.  
  
2.  Явно укажите элемент с `Me` ключевое слово.  
  
## <a name="see-also"></a>См. также

- <xref:System.MarshalByRefObject>
- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
