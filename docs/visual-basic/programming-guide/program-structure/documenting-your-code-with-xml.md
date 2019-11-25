---
title: Документирование кода с помощью XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347443"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>Документирование кода с помощью XML (Visual Basic)

In Visual Basic, you can document your code using XML

## <a name="xml-documentation-comments"></a>Комментарии XML-документации

Visual Basic provides an easy way to automatically create XML documentation for projects. You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks. With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension. Дополнительные сведения см. в разделе [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).

The XML file can be consumed or otherwise manipulated as XML. This file is located in the same directory as the output .exe or .dll file of your project.

XML documentation starts with `'''`. Обработка этих комментариев имеет некоторые ограничения.

- Документация должна представлять собой XML с правильным форматом. If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.

- Разработчики могут создавать собственные наборы тегов. There is a recommended set of tags (see "Related Sections" in this topic). Некоторые рекомендуемые теги имеют особые значения.

  - Тег \<param> используется для описания параметров. При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации. If the verification fails, the compiler issues a warning.

  - Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода. Компилятор проверяет наличие этого элемента кода. If the verification fails, the compiler issues a warning. The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.

  - The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.

## <a name="related-sections"></a>Связанные разделы

For details on creating an XML file with documentation comments, see the following topics:

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)

- [Обработка XML-файла](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Средства XML в Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>См. также

- [Разработка приложений в Visual Basic](../../../visual-basic/developing-apps/index.md)
- [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
