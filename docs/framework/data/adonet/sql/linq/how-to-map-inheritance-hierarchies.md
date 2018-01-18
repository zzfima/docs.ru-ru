---
title: "Практическое руководство. Сопоставление иерархий наследования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e9d6215335f6a58de194253cbfe1e539f50d6d84
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-map-inheritance-hierarchies"></a>Практическое руководство. Сопоставление иерархий наследования
Чтобы реализовать сопоставление наследования в [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов, как описано в следующих шагах. Сопоставить иерархии наследования пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут с помощью [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. В разделе [как: Настройка наследования с помощью реляционного конструктора объектов](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).  
  
> [!NOTE]
>  Особые атрибуты или свойства подклассов не требуются. Обратите особое внимание на то, что подклассы не имеют атрибута <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>Сопоставление иерархий наследования  
  
1.  Добавьте к корневому классу атрибут <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
2.  Кроме того, в корневом классе необходимо добавить атрибут <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> для каждого класса в структуре иерархии.  
  
3.  Определите свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> для каждого атрибута <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
     Это свойство содержит значение, которое отображается в столбце <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> таблицы базы данных и указывает, к какому классу или подклассу принадлежит эта строка данных.  
  
4.  Добавьте также для каждого атрибута <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.  
  
     Данное свойство содержит значение, которое указывает, на какой класс или подкласс указывает значение ключа.  
  
5.  Добавьте свойство <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> только к одному атрибуту <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.  
  
     Данное свойство используется для обозначения *резервной* сопоставление, когда значение дискриминатора из таблицы базы данных не соответствует ни одному <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> значение в сопоставлениях наследования.  
  
6.  Добавьте свойство <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> к атрибуту <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
     Это свойство означает, что данный столбец содержит значение <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
## <a name="example"></a>Пример  
  
> [!NOTE]
>  Пользователь среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] может настроить наследование с помощью [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. В разделе [как: Настройка наследования с помощью реляционного конструктора объектов](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 В следующем примере кода определяется корневой класс `Vehicle` и выполняются указанные выше шаги с целью описания иерархии для [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Поддержка наследования](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)  
 [Практическое руководство. Настройка классов сущностей с использованием редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
