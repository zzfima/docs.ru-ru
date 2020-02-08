---
title: Руководство по программированию на C#. <exception>
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 14318ac0b0cdf781d0488eecaf934879017d91f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789801"
---
# <a name="exception-c-programming-guide"></a>Руководство по программированию на C#. \<exception>

## <a name="syntax"></a>Синтаксис

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a>Параметры

- cref = "`member`"

  Ссылка на исключение, которое доступно из текущей среды компиляции. Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").

  См. подробнее о том, как форматировать `member`, чтобы создать ссылку на универсальный тип, в руководстве по [обработке XML-файла](processing-the-xml-file.md).

- `description`

  Описание исключения.

## <a name="remarks"></a>Примечания

Тег \<exception> служит для указания возможных исключений. Этот тег может применяться к определениям методов, свойств, событий и индексаторов.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

Дополнительные сведения об обработке исключений см. в разделе [Исключения и обработка исключений](../exceptions/index.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](recommended-tags-for-documentation-comments.md)
