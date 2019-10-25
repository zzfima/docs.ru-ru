---
title: Утверждения
description: Узнайте, как использовать выражение "Assert" в качестве функции отладки для тестирования выражений на языке F# программирования.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799063"
---
# <a name="assertions"></a>Утверждения

Выражение `assert` — это функция отладки, которую можно использовать для проверки выражения. При сбое в режиме отладки утверждение создает диалоговое окно системной ошибки.

## <a name="syntax"></a>Синтаксис

```fsharp
assert condition
```

## <a name="remarks"></a>Заметки

Выражение `assert` имеет тип `bool -> unit`.

Функция `assert` разрешается в <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Это означает, что его поведение аналогично вызову <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> напрямую.

Проверка утверждения включена только при компиляции в режиме отладки. то есть, если определена константа `DEBUG`. В системе проекта по умолчанию константа `DEBUG` определена в конфигурации отладки, но не в конфигурации выпуска.

Ошибка при сбое утверждения не может быть перехвачена с F# помощью обработки исключений.

## <a name="example"></a>Пример

В следующем примере кода показано использование выражения `assert`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
