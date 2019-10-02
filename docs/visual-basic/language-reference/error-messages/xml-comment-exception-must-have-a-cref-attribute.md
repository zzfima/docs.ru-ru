---
title: Исключение комментария XML должно иметь атрибут cref
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592030"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>Исключение комментария XML должно иметь атрибут cref
Тег \<exception > предоставляет способ документирования исключений, которые могут быть созданы методом. Обязательный атрибут `cref` обозначает имя члена, который проверяется генератором документации. Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.  
  
 **Идентификатор ошибки:** BC42319  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Добавьте в исключение атрибут `cref` следующим образом:  
  
    Xml  
    <exception cref="member">Описание</exception> "" "  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
