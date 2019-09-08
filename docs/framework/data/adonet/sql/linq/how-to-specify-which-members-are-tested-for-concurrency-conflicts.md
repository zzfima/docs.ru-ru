---
title: Практическое руководство. Как указать, для каких элементов тестируется возникновение конфликтов параллелизма
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: de7109e0fed0eb7c1975ad7360a7588ef9b294ef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793142"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a>Практическое руководство. Как указать, для каких элементов тестируется возникновение конфликтов параллелизма
Примените одно из трех перечислений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] к <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> свойству <xref:System.Data.Linq.Mapping.ColumnAttribute> атрибута, чтобы указать, какие элементы должны включаться в проверки обновления для обнаружения конфликтов оптимистичного параллелизма.  
  
 Свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> (сопоставляемое во время разработки) используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] вместе с возможностями параллелизма времени выполнения. Дополнительные сведения см. в [разделе оптимистичный параллелизм. Обзор](optimistic-concurrency-overview.md).  
  
> [!NOTE]
> Если ни одному члену не присвоено значение `IsVersion=true`, исходные значения членов сравниваются с текущим состоянием базы данных. Дополнительные сведения см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
 Примеры кода см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a>Чтобы всегда использовать этот член для обнаружения конфликтов, выполните следующие действия.  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Always`.  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a>Чтобы никогда не использовать этот член для обнаружения конфликтов, выполните следующие действия.  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `Never`.  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a>Чтобы использовать этот член для обнаружения конфликтов, только когда приложение изменяет его значение, выполните следующие действия.  
  
1. Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Задайте свойству <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> значение `WhenChanged`.  
  
## <a name="example"></a>Пример  
 В следующем примере указывается, что объекты `HomePage` никогда не должны включаться в проверки обновлений. Дополнительные сведения см. в разделе <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Управление конфликтами изменений](how-to-manage-change-conflicts.md)
- [Внесение и отправка изменений данных](making-and-submitting-data-changes.md)
