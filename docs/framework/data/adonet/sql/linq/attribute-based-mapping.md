---
title: Сопоставление, основанное на атрибутах
ms.date: 03/30/2017
ms.assetid: 6dd89999-f415-4d61-b8c8-237d23d7924e
ms.openlocfilehash: 81bbe8806694967d68c3e15da1d582092fb95e1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="attribute-based-mapping"></a>Сопоставление, основанное на атрибутах
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет базу данных SQL Server для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объектной модели, либо путем применения атрибутов или с помощью внешнего файла сопоставления. В этом разделе представлен подход на основе атрибутов.  
  
 В своей самой простой форме [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет базу данных с <xref:System.Data.Linq.DataContext>, таблицу с классом, а столбцы и связи - со свойствами этих классов. Атрибуты также можно использовать для сопоставления иерархии наследования в объектной модели. Дополнительные сведения см. в разделе [как: Создание модели объектов в Visual Basic или C#](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
 Разработчики, обычно с помощью Visual Studio выполняют сопоставление на основе атрибутов с помощью [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. Можно также использовать программу командной строки SQLMetal или вручную написать код атрибутов самостоятельно. Дополнительные сведения см. в разделе [как: Создание модели объектов в Visual Basic или C#](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
> [!NOTE]
>  Сопоставление можно также выполнять с помощью внешнего файла XML. Дополнительные сведения см. в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
 В следующих разделах представлено более подробное описание сопоставления на основе атрибутов. Дополнительные сведения см. в описании пространства имен <xref:System.Data.Linq.Mapping>.  
  
## <a name="databaseattribute-attribute"></a>Атрибут DatabaseAttribute  
 Этот атрибут используется для указания имени базы данных по умолчанию, если оно не предоставлено при подключении. Данный атрибут является необязательным, однако если он используется, следует применить свойство <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>, как описано в следующей таблице.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>|Строковое|См. раздел <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.|Используется со свойством <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>, указывает имя базы данных.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
## <a name="tableattribute-attribute"></a>Атрибут TableAttribute  
 Чтобы определить класс как класс сущности, связанный с таблицей базы данных или представлением, используется атрибут. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] интерпретирует классы, имеющие данный атрибут, как постоянные. В следующей таблице приводится описание свойства <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>|Строковое|Строка, соответствующая имени класса|Определяет класс как класс сущности, связанный с таблицей базы данных.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
## <a name="columnattribute-attribute"></a>Атрибут ColumnAttribute  
 Этот атрибут используется для назначения члена класса сущности, представляющего столбец в таблице базы данных. Этот атрибут можно применять к любому полю или свойству.  
  
 Когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сохраняет изменения в базе данных, извлекаются и сохраняются только те члены класса, которые определены как столбцы. Члены без данного атрибута считаются непостоянными и не передаются для вставок или обновлений.  
  
 В следующей таблице представлено описание свойств этого атрибута.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>|AutoSync|Никогда|Указывает среде CLR на необходимость получить значение после выполнения операции вставки или обновления.<br /><br /> Параметры: Always, Never, OnUpdate, OnInsert.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>|Boolean|`true`|Указывает, что столбец может содержать значения NULL.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>|Строковое|Определенный тип столбца базы данных|Для указания типа столбца базы данных использует типы и модификаторы базы данных.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>|Строковое|Empty|Определяет вычисляемый столбец в базе данных.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>|Boolean|`false`|Указывает, что столбец содержит значения, автоматически генерируемые базой данных.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>|Boolean|`false`|Указывает, что столбец содержит значение дискриминатора для иерархии наследования [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>|Boolean|`false`|Указывает, что этот член класса представляет столбец, входящий в состав первичных ключей таблицы.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>|Boolean|`false`|Определяет тип столбца члена как отметка времени или номер версии в базе данных.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>|UpdateCheck|`Always`, до тех пор, пока <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> имеет значение `true` для члена|Указывает, какой подход реализуется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для обнаружения конфликтов оптимистичного параллелизма.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
> [!NOTE]
>  В значениях свойства Storage для атрибутов AssociationAttribute и ColumnAttribute учитывается регистр. Например, следует убедиться в том, что регистр символов в значении, использованном в атрибуте свойства AssociationAttribute.Storage, соответствует регистру символов в соответствующих именах свойств в остальном коде. Это применяется для всех языков программирования .NET, включая те, которые обычно регистр не учитывается, включая Visual Basic. Дополнительные сведения о свойстве Storage см. в разделе <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="associationattribute-attribute"></a>Атрибут AssociationAttribute  
 Применяйте этот атрибут для указания свойства, которое будет представлять связь в базе данных, такую как отношение внешнего и первичного ключей. Дополнительные сведения о связях см. в разделе [как: сопоставление связей базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md).  
  
 В следующей таблице представлено описание свойств этого атрибута.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteOnNull%2A>|Boolean|`false`|При задании данного свойства для ассоциации, в которой члены внешнего ключа не поддерживают значение NULL, удаляет объект при установке ассоциации значения NULL.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteRule%2A>|Строковое|Нет|Добавляет в ассоциацию поведение удаления.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsForeignKey%2A>|Boolean|`false`|При значении "true" назначает член в качестве внешнего ключа в ассоциации, представляющей отношение базы данных.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsUnique%2A>|Boolean|`false`|При значении «true» указывает ограничение уникальности для первичного ключа.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>|Строковое|Идентификатор связанного класса|Назначает один или более членов целевого класса сущности в качестве ключевых значений на другой стороне ассоциации.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.ThisKey%2A>|Строковое|Идентификатор содержащего класса|Назначает элементы данного класса сущности, которые будут представлять ключевые значения на этой стороне ассоциации.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.AssociationAttribute>.  
  
> [!NOTE]
>  В значениях свойства Storage для атрибутов AssociationAttribute и ColumnAttribute учитывается регистр. Например, следует убедиться в том, что регистр символов в значении, использованном в атрибуте свойства AssociationAttribute.Storage, соответствует регистру символов в соответствующих именах свойств в остальном коде. Это применяется для всех языков программирования .NET, включая те, которые обычно регистр не учитывается, включая Visual Basic. Дополнительные сведения о свойстве Storage см. в разделе <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="inheritancemappingattribute-attribute"></a>Атрибут InheritanceMappingAttribute  
 Применяйте этот атрибут для сопоставления иерархии наследования.  
  
 В следующей таблице представлено описание свойств этого атрибута.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>|Строковое|Отсутствует. Необходимо предоставить значение.|Указывает значение кода дискриминатора.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>|Boolean|`false`|При значении "true" создает объект данного типа, когда значение дискриминатора в хранилище не соответствует ни одному заданному значению.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>|Тип|Отсутствует. Необходимо предоставить значение.|Указывает тип класса в иерархии.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>.  
  
## <a name="functionattribute-attribute"></a>Атрибут FunctionAttribute  
 Этот атрибут используется для назначения метода, представляющего хранимую процедуру или пользовательской функцию в базе данных.  
  
 В следующей таблице представлено описание свойств этого атрибута.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>|Boolean|`false`|Если значение равно false, указывает сопоставление с хранимой процедурой. При значении «true» указывает сопоставление с пользовательской функцией.|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.Name%2A>|Строковое|Строка, соответствующая имени базы данных|Указывает имя хранимой процедуры или пользовательской функции.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.FunctionAttribute>.  
  
## <a name="parameterattribute-attribute"></a>Атрибут ParameterAttribute  
 Этот атрибут используется для сопоставления входных параметров в методах хранимых процедур.  
  
 В следующей таблице представлено описание свойств этого атрибута.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.DbType%2A>|Строковое|Нет|Указывает тип базы данных.|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.Name%2A>|Строковое|Строка, соответствующая имени параметра в базе данных|Указывает имя для параметра.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ParameterAttribute>.  
  
## <a name="resulttypeattribute-attribute"></a>Атрибут ResultTypeAttribute   
 Этот атрибут используется для указания типа результата.  
  
 В следующей таблице представлено описание свойств этого атрибута.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ResultTypeAttribute.Type%2A>|Тип|(Нет)|Используется в методах, сопоставленных с хранимыми процедурами, возвращающих <xref:System.Data.Linq.IMultipleResults>. Объявляет допустимые или ожидаемые сопоставления типов для хранимых процедур.|  
  
 Для получения дополнительной информации см. <xref:System.Data.Linq.Mapping.ResultTypeAttribute>.  
  
## <a name="dataattribute-attribute"></a>Атрибут DataAttribute  
 Этот атрибут используется для указания имен и закрытых полей хранения.  
  
 В следующей таблице представлено описание свойств этого атрибута.  
  
|Свойство|Тип|По умолчанию|Описание|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>|Строковое|Строка, соответствующая имени базы данных|Указывает имя таблицы, столбца и т. д.|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>|Строковое|Открытые методы доступа|Указывает имя базового поля хранения.|  
  
 Дополнительные сведения см. в разделе <xref:System.Data.Linq.Mapping.DataAttribute>.  
  
## <a name="see-also"></a>См. также  
 [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
