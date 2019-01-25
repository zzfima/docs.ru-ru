---
title: Исключение комментария XML должно содержать &#39;cref&#39; атрибут
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 0f276781165e80b2d869da2518dbe34b33085d5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649951"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>Исключение комментария XML должно содержать &#39;cref&#39; атрибут
\<Исключение > тег предоставляет способ для документирования исключений, которые могут быть созданы с помощью метода. Необходимая `cref` атрибут назначает имя элемента, которое проверяется генератором документации. Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.  
  
 **Идентификатор ошибки:** BC42319  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Добавление `cref` атрибут исключение следующим образом:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>См. также
- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
