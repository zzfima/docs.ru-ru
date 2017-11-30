---
title: "Пользовательские функции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ff13a123bcb2c61d786f2156e600a16cdd6bb31e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="user-defined-functions"></a>Пользовательские функции
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует методы в объектной модели для представления пользовательских функций. Чтобы назначить методы в качестве функций, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>, а где необходимо - атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>. Дополнительные сведения см. в разделе [LINQ to SQL модель объектов](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Чтобы избежать <xref:System.InvalidOperationException>, пользовательские функции в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] должны быть представлены в одной из следующих форм.  
  
-   Функция, упакованная в качестве вызова метода с правильными атрибутами сопоставления. Дополнительные сведения см. в разделе [сопоставления на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   Статический метод SQL, характерный для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   Функция, поддерживаемая методом [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода. Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], как правило, пользуются конструктором [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для сопоставления определяемых пользователем функций.  
  
## <a name="in-this-section"></a>Содержание  
 [Как: используйте скалярные определяемые пользователем функции](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 Описано, как реализовать функцию, возвращающую скалярные значения.  
  
 [Как: использование возвращающих табличные значения определяемых пользователем функций](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 Содержит описание способов реализации функции, возвращающей табличные значения.  
  
 [Как: встроенный вызов пользовательских функций](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 Содержит описание преобразования встроенных вызовов в функции и представляет различия при внутреннем осуществлении вызова.
