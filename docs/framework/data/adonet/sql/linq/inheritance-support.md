---
title: "Поддержка наследования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e15f0194586cc8d4e069f04a95089cbef709581f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="inheritance-support"></a>Поддержка наследования
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]поддерживает *однотабличное сопоставление*. Другими словами, в одной таблице базы данных хранится полная иерархия наследования. Таблица содержит плоское объединение всех возможных столбцов данных для всей иерархии. (Объединение является результатом сочетания двух таблиц в одной, в которой имеются строки любой из исходных таблиц.) Каждая строка в столбцах содержит значения NULL, которые не применяются к типу экземпляра, представленного строкой.  
  
 Стратегия однотабличного сопоставления представляет собой простейшее представление наследования и обеспечивает высокую производительность для многих различных категорий запросов.  
  
 Чтобы реализовать данное сопоставление в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов. Дополнительные сведения см. в разделе [как: сопоставление иерархий наследования](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).  
  
 Для сопоставления иерархий наследования пользователь среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] может также воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  
  
## <a name="see-also"></a>См. также  
 [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
