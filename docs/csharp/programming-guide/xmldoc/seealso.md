---
title: <seealso> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: e24d5910ab21f01aebb5a32ce7646cf56886a81a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093465"
---
# <a name="seealso-c-programming-guide"></a>Руководство по программированию на C#. \<seealso>

## <a name="syntax"></a>Синтаксис

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a>Параметры

- cref = "`member`"

  Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции. Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").

  Сведения о создании ссылки cref на универсальный тип см. в статье об [атрибуте cref](./cref-attribute.md).

## <a name="remarks"></a>Примечания

Кроме того, с помощью тега \<seealso> можно указать текст, который должен отображаться в разделе "См. также". Тег [\<see>](./see.md) позволяет задать ссылку из текста.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

В разделе [\<summary>](./summary.md) можно найти пример использования тега \<seealso>.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
