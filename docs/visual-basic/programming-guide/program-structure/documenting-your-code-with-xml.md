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

В Visual Basic можно документировать код с помощью XML

## <a name="xml-documentation-comments"></a>Комментарии к XML-документации

Visual Basic предоставляет простой способ автоматического создания XML-документации для проектов. Можно автоматически создать XML-схему для типов и членов, а затем предоставить сводные данные, описательную документацию для каждого параметра и другие замечания. При соответствующей настройке XML-документация автоматически отправляется в XML-файл с тем же именем, что и у проекта, и с расширением XML. Дополнительные сведения см. в разделе [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).

XML-файл можно использовать или иным образом манипулировать как XML. Этот файл находится в том же каталоге, что и файл Output. exe или. DLL проекта.

Документация по XML начинается с `'''`. Обработка этих комментариев имеет некоторые ограничения.

- Документация должна представлять собой XML с правильным форматом. Если XML сформирован неправильно, создается предупреждение, а файл документации содержит комментарий, в котором говорится, что обнаружена ошибка.

- Разработчики могут создавать собственные наборы тегов. Рекомендуемый набор тегов (см. раздел "связанные разделы" в этой статье). Некоторые рекомендуемые теги имеют особые значения.

  - Тег \<param> используется для описания параметров. При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации. Если проверка завершается неудачно, компилятор выдает предупреждение.

  - Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода. Компилятор проверяет наличие этого элемента кода. Если проверка завершается неудачно, компилятор выдает предупреждение. Компилятор также учитывает любые операторы `Imports` при поиске типа, описанного в атрибуте `cref`.

  - Тег \<Summary > используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.

## <a name="related-sections"></a>Связанные разделы

Дополнительные сведения о создании XML-файла с комментариями к документации см. в следующих разделах:

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)

- [Обработка XML-файла](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [Практическое руководство. Создание XML-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Средства XML в Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>См. также

- [Разработка приложений в Visual Basic](../../../visual-basic/developing-apps/index.md)
- [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
