---
title: "Не может ссылаться на &#39; &lt;имя&gt;&#39; поскольку он является членом поля типизированным значением &#39;&lt; имя&gt;&#39; класс &#39;&lt; className&gt;&#39; содержит &#39; System.MarshalByRefObject &#39; как базовый класс"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords: BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a>Не может ссылаться на &#39; &lt;имя&gt;&#39; поскольку он является членом поля типизированным значением &#39;&lt; имя&gt;&#39; класс &#39;&lt; className&gt;&#39; содержит &#39; System.MarshalByRefObject &#39; как базовый класс
`System.MarshalByRefObject` Класс позволяет приложений, поддерживающих удаленный доступ к объектам через границы домена приложения. Типы должны наследовать `MarshalByRejectObject` класса при использовании типа через границы домена приложения. Состояние объекта не должны копироваться, так как члены объекта не может использоваться за пределами домена приложения, в котором они были созданы.  
  
 **Идентификатор ошибки:** BC30310  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте ссылку, чтобы убедиться в том, что член является допустимым.  
  
2.  Явно укажите элемент с `Me` ключевое слово.  
  
## <a name="see-also"></a>См. также  
 <xref:System.MarshalByRefObject>  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
