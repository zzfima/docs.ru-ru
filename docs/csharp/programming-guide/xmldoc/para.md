---
title: <para> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: b2740370106ce5b2812acbea212354ebea1f0e34
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793410"
---
# <a name="para-c-programming-guide"></a>Руководство по программированию на C#. \<para>

## <a name="syntax"></a>Синтаксис

```xml
<para>content</para>
```

## <a name="parameters"></a>Параметры

- `content`

  Текст абзаца.

## <a name="remarks"></a>Примечания

Тег \<para> используется внутри другого тега, например [\<summary>](./summary.md), [\<remarks>](./remarks.md) или [\<returns>](./returns.md), и позволяет добавить к тексту структуру.

Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).

## <a name="example"></a>Пример

В разделе [\<summary>](./summary.md) можно найти пример использования тега \<para>.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
