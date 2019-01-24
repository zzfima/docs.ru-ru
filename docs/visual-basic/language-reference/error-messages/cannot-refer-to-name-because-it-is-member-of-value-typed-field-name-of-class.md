---
title: Не может ссылаться на &#39; &lt;имя&gt; &#39; так как он является членом поля с типизированным значением &#39; &lt;имя&gt; &#39; класса &#39; &lt;classname&gt; &#39;с &#39;System.MarshalByRefObject&#39; как базовый класс
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: a6298c3e0f5102397d5cc3f237a186598c6b5ecc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739301"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>Не может ссылаться на &#39; &lt;имя&gt; &#39; так как он является членом поля с типизированным значением &#39; &lt;имя&gt; &#39; класса &#39; &lt;classname&gt; &#39;с &#39;System.MarshalByRefObject&#39; как базовый класс
`System.MarshalByRefObject` Класс позволяет приложения, поддерживающие удаленный доступ к объектам через границы домена приложения. Типы должны быть наследниками `MarshalByRejectObject` класса при использовании типа через границы домена приложения. Состояние объекта не должны копироваться, так как члены объекта не могут использоваться за пределами домена приложения, в котором они были созданы.  
  
 **Идентификатор ошибки:** BC30310  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверяет ссылку, чтобы убедиться в том, что член является допустимым.  
  
2.  Явно укажите элемент с `Me` ключевое слово.  
  
## <a name="see-also"></a>См. также
- <xref:System.MarshalByRefObject>
- [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
