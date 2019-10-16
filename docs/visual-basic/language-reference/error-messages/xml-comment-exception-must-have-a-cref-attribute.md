---
title: Исключение комментария XML должно иметь атрибут cref
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321178"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>Исключение комментария XML должно иметь атрибут cref

Тег \<exception > предоставляет способ документирования исключений, которые могут быть созданы методом. Обязательный атрибут `cref` обозначает имя члена, который проверяется генератором документации. Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.

**Идентификатор ошибки:** BC42319

## <a name="to-correct-this-error"></a>Исправление ошибки

Добавьте в исключение атрибут `cref` следующим образом:

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>См. также

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
