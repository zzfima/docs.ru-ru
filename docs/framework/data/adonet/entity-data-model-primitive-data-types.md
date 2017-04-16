---
title: "Модель EDM. Примитивные типы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Модель EDM. Примитивные типы данных
Модель EDM поддерживает набор абстрактных типов\-примитивов данных \(таких как строка, логическое выражение, Int32 и так далее\), которые используются для определения [свойств](../../../../docs/framework/data/adonet/property.md) в концептуальной модели.  Эти примитивные типы данных являются посредниками для фактических примитивных типов данных, которые поддерживаются в среде хранения или размещения, такой как база данных сервера SQL или среда CLR.  Модель EDM не определяет семантику операций или преобразований для примитивных типов данных; такая семантика определяется средой хранения или размещения.  Обычно примитивные типы данных в модели EDM сопоставляются соответствующим примитивным типам данных в среде хранения или размещения.  Дополнительные сведения о том, как платформа Entity Framework сопоставляет примитивные типы в модели EDM с типами данных сервера SQL, см. в разделе [Типы SqlClient для Entity Framework](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
> [!NOTE]
>  Модель EDM не поддерживает коллекции примитивных типов данных.  
  
 Дополнительные сведения о типах структурированных данных в модели EDM см. в разделе [тип сущности](../../../../docs/framework/data/adonet/entity-type.md) и [сложный тип](../../../../docs/framework/data/adonet/complex-type.md).  
  
## Примитивные типы данных, поддерживаемые в модели EDM  
 В приведенной ниже таблице представлены примитивные типы данных, поддерживаемые моделью EDM.  Также в таблице приводятся [аспекты](../../../../docs/framework/data/adonet/facet.md), которые могут быть применены к каждому примитивному типу данных.  
  
|Примитивный тип данных|Описание|Применимые аспекты|  
|----------------------------|--------------|------------------------|  
|Binary|Содержит двоичные данные.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|Содержит значение `true` или `false`.|Nullable, Default|  
|Byte|Содержит 8\-битное целое значение без знака.|Precision, Nullable, Default|  
|DateTime|Представляет дату и время.|Precision, Nullable, Default|  
|DateTimeOffset|Возвращает дату и время в виде смещения в минутах от времени GMT.|Precision, Nullable, Default|  
|Десятичное число|Содержит точное числовое значение с заданной точностью и масштабом.|Precision, Nullable, Default|  
|Double|Содержит число с плавающей запятой с точностью до 15 цифр.|Precision, Nullable, Default|  
|Float|Содержит число с плавающей запятой с точностью до 7 цифр.|Precision, Nullable, Default|  
|Guid|Содержит уникальный 16\-битный идентификатор.|Precision, Nullable, Default|  
|Int16|Содержит 16\-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Int32|Содержит 32\-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Int64|Содержит 64\-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|SByte|Содержит 8\-разрядное целое значение со знаком.|Precision, Nullable, Default|  
|Строковое|Содержит символьные данные.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|Время|Содержит время дня.|Precision, Nullable, Default|  
  
## См. также  
 [Основные понятия модели EDM](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md)