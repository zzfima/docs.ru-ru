---
title: ". (Доступ к членам) (язык Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c90c908e567ac05f344292411978ff0c80919a65
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="-member-access-entity-sql"></a>. (Доступ к членам) (язык Entity SQL)
Точка (.) является [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор доступа к члену. Оператор доступа к элементу можно использовать, чтобы выдавать значение свойства или поля экземпляра структурного типа концептуальной модели.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Экземпляр структурного типа концептуальной модели.  
  
 `identifier`  
 Свойство или поле, принадлежащее экземпляру объекта.  
  
## <a name="remarks"></a>Примечания  
 Оператор «точка» (.) можно использовать для извлечения полей из записи подобно извлечению свойств сложного типа или типа сущности. Например, если «n» типа Name является элементом типа Name, а «p» является элементом типа Person, то «p.n» будет допустимым выражением доступа к элементу, которое выдаст значение типа Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
