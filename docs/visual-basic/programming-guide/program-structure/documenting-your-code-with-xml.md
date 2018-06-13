---
title: Документирование кода с помощью XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: fa642adcfea9e80b41b5fc148df2b95b8fa44d88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650505"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Документирование кода с помощью XML (Visual Basic)
В Visual Basic можно выполнять документирование кода с помощью XML  
  
## <a name="xml-documentation-comments"></a>Комментарии к XML-документации  
 Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов. Можно автоматически создавать схема XML для типов и членов, а также введите сводку, описательную документацию для каждого параметра и другие примечания. С соответствующей настройкой автоматически создается XML-документации в XML-файл с тем же именем, как проект и расширением XML. Дополнительные сведения см. в разделе [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
 XML-файл можно использовать или обрабатываться как XML. Этот файл находится в том же каталоге, что и выходной файл .exe или .dll проекта.  
  
 XML-документации начинается с `'''`. Обработка этих комментариев имеет некоторые ограничения.  
  
-   Документация должна представлять собой XML с правильным форматом. Если XML не имеет правильного формата, выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.  
  
-   Разработчики могут создавать собственные наборы тегов. Отсутствует рекомендуемый набор тегов (см. «Связанные разделы» в этом разделе). Некоторые рекомендуемые теги имеют особые значения.  
  
    -   Тег \<param> используется для описания параметров. При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации. Если проверка завершается ошибкой, компилятор выдает предупреждение.  
  
    -   Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода. Компилятор проверяет, что этот элемент кода существует. Если проверка завершается ошибкой, компилятор выдает предупреждение. Компилятор также учитывает любые `Imports` инструкции при поиске типа, описанного в `cref` атрибута.  
  
    -   \<Сводки > тег используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о тип или член.  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения о создании XML-файла в комментарии документации в следующих разделах:  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [Обработка XML-файла](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Средства XML в Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>См. также  
 [Разработка приложений в Visual Basic](../../../visual-basic/developing-apps/index.md)  
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
