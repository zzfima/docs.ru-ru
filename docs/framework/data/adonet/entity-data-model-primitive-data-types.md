---
title: 'EDM (модель данных с использованием сущностей): примитивные типы данных'
ms.date: 03/30/2017
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
ms.openlocfilehash: 044a0ed981bb9cda3550fb3a3a9f1cb9bff96f25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667136"
---
# <a name="entity-data-model-primitive-data-types"></a>EDM (модель данных с использованием сущностей): примитивные типы данных
Entity Data Model (EDM) поддерживает набор абстрактных примитивных типов данных (например, строка, логическое значение, Int32 и т. д.), которые используются для определения [свойства](../../../../docs/framework/data/adonet/property.md) в концептуальной модели. Эти примитивные типы данных являются посредниками для фактических примитивных типов данных, которые поддерживаются в среде хранения или размещения, такой как база данных сервера SQL или среда CLR. Модель EDM не определяет семантику операций или преобразований для примитивных типов данных; такая семантика определяется средой хранения или размещения. Обычно примитивные типы данных в модели EDM сопоставляются соответствующим примитивным типам данных в среде хранения или размещения. Сведения о том, как Entity Framework сопоставляет примитивные типы в модели EDM с типами данных SQL Server, см. в разделе [сущности типы SqlClient для](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
>  Модель EDM не поддерживает коллекции примитивных типов данных.  
  
 Сведения о типах структурированных данных в модели EDM, см. в разделе [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) и [сложного типа](../../../../docs/framework/data/adonet/complex-type.md).  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>Примитивные типы данных, поддерживаемые в модели EDM  
 В приведенной ниже таблице представлены примитивные типы данных, поддерживаемые моделью EDM. В таблице также перечислены [аспекты](../../../../docs/framework/data/adonet/facet.md) , которые могут быть применены к каждому примитивному типу данных.  
  
|Примитивный тип данных|Описание|Применимые аспекты|  
|-------------------------|-----------------|-----------------------|  
|Бинарный|Содержит двоичные данные.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|Содержит значение `true` или `false`.|Nullable, Default|  
|Byte|Содержит 8-битное целое значение без знака.|Precision, Nullable, Default|  
|DateTime|Представляет дату и время.|Precision, Nullable, Default|  
|DateTimeOffset|Возвращает дату и время в виде смещения в минутах от времени GMT.|Precision, Nullable, Default|  
|Десятичное число|Содержит точное числовое значение с заданной точностью и масштабом.|Precision, Nullable, Default|  
|Double|Содержит число с плавающей запятой с точностью до 15 цифр.|Precision, Nullable, Default|  
|Float|Содержит число с плавающей запятой с точностью до 7 цифр.|Precision, Nullable, Default|  
|Guid|Содержит уникальный 16-битный идентификатор.|Precision, Nullable, Default|  
|Int16|Содержит 16-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Int32|Содержит 32-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Int64|Содержит 64-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|SByte|Содержит 8-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|String|Содержит символьные данные.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|Время|Содержит время дня.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>См. также

- [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Сущностная модель данных](../../../../docs/framework/data/adonet/entity-data-model.md)
