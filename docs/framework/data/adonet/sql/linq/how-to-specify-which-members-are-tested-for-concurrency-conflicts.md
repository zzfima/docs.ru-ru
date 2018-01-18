---
title: "Практическое руководство. Выбор членов для проверки на конфликты параллельности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0c65299f48db3ba727cece673e6a7df2d9cd8872
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a>Практическое руководство. Выбор членов для проверки на конфликты параллельности
Применить один из трех перечислений к [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> свойство <xref:System.Data.Linq.Mapping.ColumnAttribute> проверяет атрибут, чтобы указать, какие члены должны быть включены в обновления для обнаружения конфликтов оптимистичного параллелизма.  
  
 Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> (сопоставляемое во время разработки) используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вместе с функциями параллелизма времени выполнения. Дополнительные сведения см. в разделе [оптимистичного параллелизма: Обзор](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  Если ни одному члену не присвоено значение `IsVersion=true`, исходные значения членов сравниваются с текущим состоянием базы данных. Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a>Чтобы всегда использовать этот член для обнаружения конфликтов, выполните следующие действия.  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Always`.  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a>Чтобы никогда не использовать этот член для обнаружения конфликтов, выполните следующие действия.  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Never`.  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a>Чтобы использовать этот член для обнаружения конфликтов, только когда приложение изменяет его значение, выполните следующие действия.  
  
1.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `WhenChanged`.  
  
## <a name="example"></a>Пример  
 В следующем примере указывается, что объекты `HomePage` никогда не должны включаться в проверки обновлений. Дополнительные сведения см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Управление конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Внесение и отправка изменений данных](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
