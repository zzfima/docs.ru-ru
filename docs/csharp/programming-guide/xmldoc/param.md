---
title: <param> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789759"
---
# <a name="param-c-programming-guide"></a>Руководство по программированию на C#. \<param>

## <a name="syntax"></a>Синтаксис

```xml
<param name="name">description</param>
```

## <a name="parameters"></a>Параметры

- `name`

  Имя параметра метода. Имя заключается в двойные кавычки (" ").

- `description`

  Описание параметра.

## <a name="remarks"></a>Примечания

Тег \<param> следует использовать в комментариях к объявлению метода для описания одного из параметров такого метода. Чтобы задокументировать несколько параметров, используйте несколько тегов \<param>.

Текст тега \<param> будет отображаться в IntelliSense, в окне обозревателя объектов и в веб-отчете по комментариям к коду.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
