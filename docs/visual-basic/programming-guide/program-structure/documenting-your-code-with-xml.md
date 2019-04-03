---
title: Документирование кода с помощью XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: 9b53b73afb9c6b793597c00fd2eb029b18bf1f9a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831583"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Документирование кода с помощью XML (Visual Basic)
В Visual Basic можно документировать код с помощью XML  
  
## <a name="xml-documentation-comments"></a>Комментарии к XML-документации  
 Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов. Можно автоматически создавать схема XML для типов и членов и введите сводку, описательную документацию для каждого параметра и другие примечания. С соответствующей настройкой XML-документации автоматически генерируется в файл XML с именем проекта и расширение XML. Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 XML-файле может быть использоваться или обрабатываться как XML. Этот файл находится в том же каталоге, что и выходной файл .exe или .dll проекта.  
  
 Документация XML начинается с `'''`. Обработка этих комментариев имеет некоторые ограничения.  
  
-   Документация должна представлять собой XML с правильным форматом. Если XML-код сформирован неправильно, выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.  
  
-   Разработчики могут создавать собственные наборы тегов. Есть рекомендуемый набор тегов (см. в разделе «Связанные разделы» этой статьи). Некоторые рекомендуемые теги имеют особые значения.  
  
    -   Тег \<param> используется для описания параметров. При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации. При сбое проверки компилятор выдает предупреждение.  
  
    -   Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода. Компилятор проверяет наличие этого элемента кода. При сбое проверки компилятор выдает предупреждение. Компилятор также учитывает любые `Imports` инструкции при поиске типа, описанного в `cref` атрибута.  
  
    -   \<Summary > тег используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типа или члена.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения о создании файла XML с комментариями документации см. в разделах:  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)  
  
-   [Обработка XML-файла](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Средства XML в Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>См. также

- [Разработка приложений в Visual Basic](../../../visual-basic/developing-apps/index.md)
- [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
