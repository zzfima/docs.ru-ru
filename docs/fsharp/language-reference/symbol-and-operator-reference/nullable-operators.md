---
title: Операторы, допускающие значение NULL (F#)
description: 'Дополнительные сведения об операторах допускает значения NULL, доступные в языке F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 63ad7da2d584b96eee8765b57fc671befbcbd38b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566354"
---
# <a name="nullable-operators"></a>Операторы, допускающие значение NULL

Операторы, допускающие значения NULL являются бинарные операторы арифметический тип или сравнения, которые работают с арифметические типы, допускающие значение NULL, на обеих сторонах. Типы, допускающие значения NULL возникают часто при работе с данными из источников, таких как базы данных, допускающих значение NULL вместо фактических значений. В выражениях запросов часто используются операторы, допускающие значение NULL. Помимо nullable операторы для арифметических и сравнения можно использовать операторы преобразования для преобразования между типами значения NULL. Существуют также допускает значения NULL версии определенных операторов.


## <a name="table-of-nullable-operators"></a>Таблица операторов, допускающие значение NULL
В следующей таблице перечислены значения NULL операторы, поддерживаемые в языке F #.

|Nullable слева|Nullable справа|Обе стороны допускает значения NULL|
|---|---|---|
|[?>=](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[>=?](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[?>=?](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[?>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[>?](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[?>?](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[?<=](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<=?](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[?<=?](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[?<](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<?](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[?<?](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[?=](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[=?](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[?=?](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[?<>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<>?](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[?<>?](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[?+](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[+?](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[?+?](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[?-](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[-?](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[?-?](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[?*](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[*?](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[?*?](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[?/](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[/?](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[?/?](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[?%](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[%?](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[?%?](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a>Примечания
Операторы, допускающие значение NULL, включаются в [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) модуля в пространстве имен [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d). Тип данных допускает значения NULL — `System.Nullable<'T>`.

В выражениях запросов допускающих значение NULL типов возникают при выборе данных из источника данных, допускающий значения NULL, а не значения. В базе данных SQL Server каждый столбец в таблице имеет атрибут, который указывает, допускаются ли значения NULL. Если допускаются значения NULL, данные, возвращенные из базы данных может содержать значения NULL, не может быть представлен примитивный тип данных таких как `int`, `float`, и т. д. Таким образом, данные возвращаются в виде `System.Nullable<int>` вместо `int`, и `System.Nullable<float>` вместо `float`. Фактическое значение можно получить из `System.Nullable<'T>` объектов с помощью `Value` , а также можно определить, если `System.Nullable<'T>` объект имеет значение путем вызова `HasValue` метод. Другим полезным методом является `System.Nullable<'T>.GetValueOrDefault` метод, который позволяет получать значение или значение по умолчанию соответствующего типа. Значение по умолчанию — определенные виды «ноль» значение, например 0, 0,0, или `false`.

Типы, допускающие значение NULL может быть преобразован в запретом типы-примитивы, такие как с помощью операторов преобразования обычные `int` или `float`. Можно также преобразовать один тип, допускающий значение NULL в другой тип, допускающий значение NULL, используя операторы преобразования для типов, допускающих значение NULL. Операторы соответствующее преобразование имеют имя, совпадающее с именем стандартными, но они находятся в отдельном модуле [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) модуля в [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) пространства имен. Как правило при работе с выражениями запроса откройте это пространство имен. В этом случае можно использовать операторы преобразования значения NULL, добавляя префикс `Nullable.` оператору соответствующее преобразование, как показано в следующем коде.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

В результате получается `10.000000`.

Запросов операторы для полей данных допускает значения NULL, например `sumByNullable`, также существует для использования в выражениях запросов. Операторы запросов для типов, не допускающим не совместимый с типом с типы, допускающие значение NULL, поэтому NULL версию оператора соответствующего запроса необходимо использовать при работе со значениями данных допускает значения NULL. Дополнительные сведения см. в разделе [выражения запросов](../query-expressions.md).

В следующем примере показано использование операторы, допускающие значение NULL в выражении запроса F #. Первый запрос отображает, как написать запрос без оператора допускает значение NULL; второй запрос показан эквивалентный запрос, использующий оператор допускает значения NULL. Для полного контекста, включая способы настройки базы данных, чтобы использовать этот пример кода в разделе [Пошаговое руководство: доступ к базе данных SQL с помощью поставщиков типов](../../tutorials/type-providers/accessing-a-sql-database.md).

```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq

[<Generate>]
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">

let db = dbSchema.GetDataContext()

query {
    for row in db.Table2 do
    where (row.TestData1.HasValue && row.TestData1.Value > 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="see-also"></a>См. также

[Поставщики типов](../../tutorials/type-providers/index.md)

[Выражения запросов](../query-expressions.md)
