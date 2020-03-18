---
title: Руководство по программированию на C#. <typeparamref>
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789663"
---
# <a name="typeparamref-c-programming-guide"></a>Руководство по программированию на C#. \<typeparamref>

## <a name="syntax"></a>Синтаксис

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a>Параметры

- `name`

  Имя параметра типа. Имя заключается в двойные кавычки (" ").

## <a name="remarks"></a>Remarks

Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../generics/index.md).

Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
