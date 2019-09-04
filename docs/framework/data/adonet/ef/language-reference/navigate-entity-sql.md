---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 2c6c2ae4c593da1d5fe8cdf3015eb0e31e4b12b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249941"
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

Производит переход по связи, установленной между сущностями.

## <a name="syntax"></a>Синтаксис

```
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>Аргументы

`instance-expression`Экземпляр сущности.

`relationship-type`Имя типа связи из CSDL-файла языка определения схемы. Является полным именем \<> пространства имен.\< `relationship-type` имя типа отношения >.

`to`Конец связи.

`from`Начало связи.

## <a name="return-value"></a>Возвращаемое значение

Если количество элементов в конечной составляющей связи равно 1, то будет возвращено значение `Ref<T>`. Если же количество элементов в конечной составляющей связи равно n, то будет возвращено значение `Collection<Ref<T>>`.

## <a name="remarks"></a>Примечания

Связи — это конструкции первого класса в EDM (EDM). Связи могут устанавливаться между двумя или несколькими типами сущностей, а пользователи могут переходить по связи от одного элемента (от одной сущности) к другому. `from` и `to` являются необязательными при том условии, что нет неоднозначности в разрешении имен в пределах связи.

Оператор NAVIGATE является допустимым в пространствах O и C.

Конструкция перехода имеет следующую общую форму.

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

Например:

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

Здесь OrderCustomer является значением параметра `relationship`, а Customer и Order являются элементами связи `to-end` (customer) и `from-end` (order). Если ордеркустомер является отношением n:1, то тип результата выражения Navigate является ссылочным\<> клиента.

Для этого выражение существует следующая упрощенная форма.

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

Аналогично, в запросе следующей формы выражение Navigate выдает коллекцию < порядок ссылок\<> >.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

Выражение экземпляра должно иметь тип сущности или ссылки.

## <a name="example"></a>Пример

В следующем запросе Entity SQL оператор NAVIGATE используется для перехода по связи, заданной между типами сущностей Address и SalesOrderHeader. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.

1. Выполните процедуру, описанную в [разделе инструкции. Выполнение запроса, возвращающего Структуралтипе](../how-to-execute-a-query-that-returns-structuraltype-results.md)результаты.

2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :

 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]

## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Практическое руководство. Навигация по связям с помощью оператора Navigate](navigate-entity-sql.md)
