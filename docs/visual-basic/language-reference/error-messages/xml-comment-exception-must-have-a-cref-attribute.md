---
title: "Исключение комментария XML должно содержать &#39; cref &#39; атрибут"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords: BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c22c9cd9415faf17d027c3751d166662a92b50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>Исключение комментария XML должно содержать &#39; cref &#39; атрибут
\<Исключение > тег предоставляет способ документирования исключений, которые могут быть созданы с помощью метода. Необходимая `cref` атрибут назначает имя элемента, которое проверяется генератором документации. Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.  
  
 **Идентификатор ошибки:** BC42319  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Добавить `cref` атрибут исключение следующим образом:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>См. также  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
