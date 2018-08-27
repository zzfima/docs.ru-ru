---
title: Исключение комментария XML должно содержать &#39;cref&#39; атрибут
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930032"
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
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
