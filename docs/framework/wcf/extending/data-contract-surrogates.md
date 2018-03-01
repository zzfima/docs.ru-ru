---
title: "Суррогаты контрактов данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data contracts [WCF], surrogates
ms.assetid: 8c31134c-46c5-4ed7-94af-bab0ac0dfce5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f6fcae1989b75a668fd6ff38596b06feca7be9e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="data-contract-surrogates"></a>Суррогаты контрактов данных
Контракт данных *символов-заместителей* является дополнительным, встроенная в модель контракта данных. Эта возможность предназначена для настройки и подстановки типов, когда необходимо изменить способ сериализации типа, десериализации или преобразования типа в метаданные. Например, суррогат может использоваться в сценариях, когда для типа не задан контракт данных, поля и свойства не помечены атрибутом <xref:System.Runtime.Serialization.DataMemberAttribute> или пользователи хотят динамически создавать вариации схемы.  
  
 Сериализация и десериализация выполняются с суррогатом контракта данных при использовании <xref:System.Runtime.Serialization.DataContractSerializer> для преобразования из .NET Framework в подходящий формат, например XML. Суррогат контракта данных также может использоваться для изменения метаданных, экспортированных для типов, при создании представлений метаданных, например документов схемы XML (XSD). Во время импорта из метаданных создается код, суррогат может также использоваться для настройки создаваемого кода.  
  
## <a name="how-the-surrogate-works"></a>Как работает суррогат  
 Суррогат сопоставляет один тип ("исходный" тип) с другим типом ("суррогатным" типом). В следующем примере показаны исходный тип `Inventory` и новый суррогатный тип `InventorySurrogated`. Тип `Inventory` не позволяет сериализацию, а тип `InventorySurrogated` позволяет:  
  
 [!code-csharp[C_IDataContractSurrogate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#1)]  
  
 Так как для этого класса контракт данных не определен, класс преобразуется в суррогатный класс с контрактом данных. Суррогатный класс показан в следующем примере:  
  
 [!code-csharp[C_IDataContractSurrogate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#2)]  
  
## <a name="implementing-the-idatacontractsurrogate"></a>Реализация IDataContractSurrogate  
 Для использования суррогата контракта данных необходимо реализовать интерфейс <xref:System.Runtime.Serialization.IDataContractSurrogate>.  
  
 Ниже приведен обзор каждого метода интерфейса <xref:System.Runtime.Serialization.IDataContractSurrogate> с возможной реализацией.  
  
### <a name="getdatacontracttype"></a>GetDataContractType  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A> сопоставляет один тип с другим. Этот метод требуется для сериализации, десериализации, импорта и экспорта.  
  
 Первая задача - определить, какие типы будут сопоставляться с другими типами. Пример:  
  
 [!code-csharp[C_IDataContractSurrogate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#3)]  
  
-   При сериализации сопоставление, которое возвращает этот метод, используется затем для преобразования исходного экземпляра в суррогатный экземпляр вызовом метода <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>.  
  
-   При десериализации сопоставление, которое возвращает этот метод, используется сериализатором для десериализации в экземпляр суррогатного типа. Затем вызывается метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%2A> для преобразования суррогатного экземпляра в экземпляр исходного типа.  
  
-   При экспорте суррогатный тип, возвращенный этим методом, применяется для получения контракта данных, который будет использоваться для генерирования метаданных.  
  
-   При импорте исходный тип заменяется на суррогатный, который применяется для получения контракта данных, необходимого, например для поддержки возможности ссылок.  
  
 Параметр <xref:System.Type> является типом объекта, который подвергается сериализации, десериализации, импорту или экспорту. Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A> должен возвращать тип, который был на входе, если суррогат не обрабатывает тип. В противном случае возвращается соответствующий суррогатный тип. Если существует несколько суррогатных типов, метод позволяет определить несколько сопоставлений.  
  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A> не вызывается для встроенных примитивов контрактов данных, например <xref:System.Int32> или <xref:System.String>. Для других типов, таких как массивы, типы, определяемые пользователем, и других структур данных, метод вызывается для каждого типа.  
  
 В предыдущем примере метод проверяет, совместим ли параметр `type` и `Inventory`. Если да, то метод сопоставляет его с `InventorySurrogated`. Каждый раз при сериализации, десериализации, импорте схемы или экспорте схемы сперва вызывается эта функция для определения соответствия типов.  
  
### <a name="getobjecttoserialize-method"></a>Метод GetObjectToSerialize  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A> преобразует экземпляр исходного типа в экземпляр суррогатного типа. Этот метод требуется для сериализации.  
  
 На втором этапе необходимо определить, каким образом физические данные из исходного экземпляра будут преобразовываться в данные суррогатного, при помощи реализации метода <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>. Пример:  
  
 [!code-csharp[C_IDataContractSurrogate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#4)]  
  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A> вызывается при сериализации объекта. Этот метод передает данные из исходного типа в поля суррогатного типа. Поля могут быть напрямую сопоставлены с суррогатными полями, либо в суррогате можно сохранить результат манипуляций с исходными данными. Некоторые варианты использования: прямое сопоставление полей; выполнение операций над данными, которые нужно сохранить в суррогатных полях; сохранение XML исходного типа в суррогатном поле.  
  
 Параметр `targetType` относится к объявленному типу элемента. Этот параметр является суррогатным типом, возвращенным методом <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A>. Сериализатор не требует, чтобы возвращенный объект можно было назначить этому типу. `obj` Представляет собой объект для сериализации и будут преобразованы в свой суррогат, при необходимости. Этот метод возвращает входной объект, если суррогатный не обрабатывает этот объект. В противном случае возвращается новый суррогатный объект. Суррогат не вызывается, если объект пустой. Метод позволяет определить несколько суррогатных сопоставлений для различных экземпляров.  
  
 При создании объекта <xref:System.Runtime.Serialization.DataContractSerializer> можно задать для него сохранение ссылок на объекты. ([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Сериализации и десериализации](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).) Это можно сделать, указав для параметра `preserveObjectReferences` в его конструкторе значение `true`. В таком случае суррогат вызывается для объекта только один раз, так как все последующие сериализации просто записывают в поток ссылку. Если параметр `preserveObjectReferences` имеет значение `false`, суррогат вызывается для каждого вхождения экземпляра.  
  
 Если тип экземпляра, подвергающегося сериализации, отличается от объявленного типа, сведения о типе записываются в поток (например `xsi:type`), чтобы экземпляр затем можно было десериализовать. Это происходит независимо от того, является объект суррогатным, или нет.  
  
 В приведенном выше примере данные экземпляра `Inventory` преобразуются в данные `InventorySurrogated`. Проверяется тип объекта и выполняются необходимые операции для преобразования в суррогатный тип. В данном случае поля класса `Inventory` напрямую копируются в поля класса `InventorySurrogated`.  
  
### <a name="getdeserializedobject-method"></a>Метод GetDeserializedObject  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%2A> преобразует экземпляр суррогатного типа в экземпляр исходного типа. Этот метод требуется для десериализации.  
  
 Следующая задача - определить, каким образом физические данные из суррогатного экземпляра будут сопоставляться с данными исходного экземпляра. Пример:  
  
 [!code-csharp[C_IDataContractSurrogate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#5)]  
  
 Этот метод вызывается только во время десериализации объекта. Он предоставляет возможность обратного сопоставления данных для десериализации из суррогатного типа обратно в исходный тип. Аналогично методу `GetObjectToSerialize`, возможен прямой обмен данными полей, выполнение операций над данными или хранение XML-данных. При десериализации не всегда получаются данные, идентичные исходным, что связано с операциями при преобразовании данных.  
  
 Параметр `targetType` относится к объявленному типу элемента. Этот параметр является суррогатным типом, возвращенным методом `GetDataContractType`. `obj` Параметр ссылается на объект, который был десериализован. Объект может быть преобразован обратно в свой исходный тип, если он был заменен на суррогатный. Этот метод возвращает входной объект, если суррогатный не обрабатывает этот объект. В противном случае после завершения преобразования возвращается десериализованный объект. Если есть несколько суррогатных типов, можно задать преобразование данных из суррогатного типа в исходный для каждого из них, указав каждый тип и его преобразование.  
  
 Когда возвращается объект, внутренние таблицы объектов обновляются, получая объект, возвращенный суррогатом. Все дальнейшие ссылки на экземпляр будут получать суррогатный экземпляр из таблиц объектов.  
  
 В предшествующем примере объекты типа `InventorySurrogated` преобразуются обратно в исходный тип `Inventory`. В данном случае данные напрямую передаются из полей `InventorySurrogated` в соответствующие поля `Inventory`. Так как операций с данными не производилось, все поля элементов будут содержать те же данные, что и до сериализации.  
  
### <a name="getcustomdatatoexport-method"></a>Метод GetCustomDataToExport  
 При экспорте схемы метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%2A> является необязательным. Он применяется для вставки дополнительных данных или указаний в экспортированную схему. Дополнительные данные могут быть добавлены на уровне элемента или типа. Пример:  
  
 [!code-csharp[C_IDataContractSurrogate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#6)]  
  
 Этот метод (с двумя перегрузками) позволяет включение дополнительных сведений в метаданные на уровне элемента или типа. Можно добавить указания о том, является ли элемент открытым или закрытым, а также комментарии, которые сохраняются при экспорте и импорте схемы. Если не применять этот метод, такая информация теряется. Этот метод не позволяет добавлять или удалять элементы и типы, а дает возможность добавлять дополнительные данные в схемы на любом из этих двух уровней.  
  
 Этот метод перегружен и может принимать либо объект `Type` (параметр `clrtype`), либо объект <xref:System.Reflection.MemberInfo> (параметр `memberInfo`). Второй параметр всегда будет объектом `Type` (параметр `dataContractType`). Этот метод вызывается для каждого элемента и типа суррогатного типа `dataContractType`.  
  
 Каждая из перегрузок возвращает либо `null`, либо объект, который можно сериализовать. Непустой объект сериализуется как заметка в экспортированной схеме. Для перегрузки `Type` каждый тип, экспортированный в схему, предается этому методу в первом параметре с суррогатным типом в качестве параметра `dataContractType`. Для перегрузки `MemberInfo` каждый элемент, экспортированный в схему, отправляет свои сведения как параметр `memberInfo` с суррогатным типом в качестве второго параметра.  
  
#### <a name="getcustomdatatoexport-method-type-type"></a>Метод GetCustomDataToExport (Type, Type)  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%28System.Type%2CSystem.Type%29?displayProperty=nameWithType> вызывается во время экспорта схемы для каждого определения типа. Этот метод добавляет информацию в типы схемы при экспорте. Каждый определенный тип отправляется этому методу с целью определить, есть ли дополнительные данные, которые необходимо включить в схему.  
  
#### <a name="getcustomdatatoexport-method-memberinfo-type"></a>Метод GetCustomDataToExport (MemberInfo, Type)  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=nameWithType> вызывается во время экспорта для каждого элемента в экспортируемых типах. Эта функция дает возможность настроить для элементов любые комментарии, которые будут включены в схему при экспорте. Сведения для каждого элемента класса отправляются в этот метод для проверки, не нужно ли включить в схему какие-либо дополнительные данные.  
  
 В приведенном выше примере выполняется поиск по `dataContractType` для каждого элемента суррогата. Затем возвращается соответствующий модификатор доступа для каждого поля. Без такой настойки значение по умолчанию для любого модификатора доступа - открытый. Поэтому в коде, сгенерированном при помощи экспортированной схемы, все элементы будут определены как открытые, независимо от их реальных ограничений доступа. Если бы эта реализация не использовалась, элемент `numpens` был бы открытым в экспортированной схеме, хотя он определен как закрытый в суррогате. Благодаря этому методу в экспортированной схеме модификатор доступа может быть сгенерирован как закрытый.  
  
### <a name="getreferencedtypeonimport-method"></a>Метод GetReferencedTypeOnImport  
 Этот метод сопоставляет тип <xref:System.Type> суррогата с исходным типом. Этот метод является необязательным для импорта схем.  
  
 При создании суррогата, импортирующего схему и генерирующего код для нее, следующая задача - перейти от типа суррогатного экземпляра к исходному типу.  
  
 Если в сгенерированном коде необходимо сослаться на существующий пользовательский тип, это можно сделать реализацией метода <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%2A>.  
  
 При импорте схемы этот метод вызывается для каждого объявления типа, чтобы сопоставить суррогатный контракт данных с типом. Строковые параметры `typeName` и `typeNamespace` определяют имя и пространство имен суррогатного типа. Возвращаемое значение для метода <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%2A> используется для определения, нужно ли сгенерировать новый тип. Этот метод возвращает либо допустимый тип, либо значение NULL. В случае допустимого типа возвращаемый тип используется как тип, на который существует ссылка в сгенерированном коде. Если возвращается значение NULL, ссылки на тип не будет, должен быть создан новый тип. Если есть несколько суррогатов, можно выполнить сопоставление каждого суррогатного типа и его исходного типа.  
  
 Параметр `customData` является объектом, возвращенным методом <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%2A>. Параметр `customData` используется, когда создатели суррогата хотят поместить дополнительные данные или указания в метаданные, которые используются при импорте для генерирования кода.  
  
### <a name="processimportedtype-method"></a>Метод ProcessImportedType  
 Метод <xref:System.Runtime.Serialization.IDataContractSurrogate.ProcessImportedType%2A> позволяет настроить любой тип, созданный при импорте схемы. Этот метод является необязательным.  
  
 При импорте схемы этот метод позволяет настройку любого импортированного типа и сведений о компиляции. Пример:  
  
 [!code-csharp[C_IDataContractSurrogate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#7)]  
  
 Во время импорта этот метод вызывается для каждого генерируемого типа. Измените объект <xref:System.CodeDom.CodeTypeDeclaration> или <xref:System.CodeDom.CodeCompileUnit>. Это означает в том числе изменение имени, элементов, атрибутов и многих других свойств объекта `CodeTypeDeclaration`. Обрабатывая объект `CodeCompileUnit`, можно изменить директивы, пространства имен, сборки, на которые существуют ссылки, и некоторые другие аспекты.  
  
 Параметр `CodeTypeDeclaration` содержит объявление типа Code DOM. Параметр `CodeCompileUnit` позволяет изменение обработки кода.  Если возвращается результат `null`, в объявлении типа он уничтожается. В противном случае, если возвращается объект `CodeTypeDeclaration`, изменения сохраняются.  
  
 Если при экспорте метаданных добавляются пользовательские данные, необходимо, чтобы они были предоставлены пользователю при импорте для их использования. Такие пользовательские данные могут использоваться для указаний о модели программирования или других комментариев. Каждый экземпляр `CodeTypeDeclaration` и <xref:System.CodeDom.CodeTypeMember> включает в себя пользовательские данные в виде свойства <xref:System.CodeDom.CodeObject.UserData%2A>, приведенного к типу `IDataContractSurrogate`.  
  
 В приведенном выше примере в импортированной схеме производится несколько изменений. Код сохраняет закрытые элементы исходного типа при помощи суррогата. При импорте схемы модификатор доступа по умолчанию имеет значение `public` (открытый). Поэтому все элементы суррогатной схемы будут открытыми, если не изменить их, как в этом примере. При экспорте в метаданные вставляются пользовательские данные, указывающие, какие элементы являются закрытыми. Производится поиск в пользовательских данных и проверка, должен ли модификатор доступа быть закрытым. Затем выполняется изменение соответствующего элемента, он делается закрытым при помощи атрибутов. Без такой настройки элемент `numpens` был бы определен как открытый вместо закрытого.  
  
### <a name="getknowncustomdatatypes-method"></a>Метод GetKnownCustomDataTypes  
 Этот метод получает определенные типы пользовательских данных из схемы. Этот метод является необязательным для импорта схем.  
  
 Этот метод вызывается в начале экспорта или импорта схемы. Метод возвращает типы пользовательских данных, которые используются в экспортируемой или импортируемой схеме. Методу передается объект <xref:System.Collections.ObjectModel.Collection%601> (параметр `customDataTypes`), который представляет собой коллекцию типов. Метод добавляет дополнительные известные типы в эту коллекцию. Известные типы пользовательских данных необходимы для сериализации и десериализации пользовательских данных при помощи <xref:System.Runtime.Serialization.DataContractSerializer>. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## <a name="implementing-a-surrogate"></a>Реализация суррогата  
 Чтобы использовать суррогат контракта данных в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], необходимо следовать определенным процедурам.  
  
### <a name="to-use-a-surrogate-for-serialization-and-deserialization"></a>Использование суррогата для сериализации и десериализации  
 Для выполнения сериализации и десериализации данных с суррогатом используйте <xref:System.Runtime.Serialization.DataContractSerializer>. Объект <xref:System.Runtime.Serialization.DataContractSerializer> создается при помощи <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>. Необходимо также задать суррогат.  
  
##### <a name="to-implement-serialization-and-deserialization"></a>Реализация сериализации и десериализации  
  
1.  Создайте экземпляр <xref:System.ServiceModel.ServiceHost> для службы. Полные инструкции см. в разделе [базовое Программирование WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
2.  Для каждого объекта <xref:System.ServiceModel.Description.ServiceEndpoint> заданного узла службы найдите соответствующий объект <xref:System.ServiceModel.Description.OperationDescription>.  
  
3.  Выполните поиск экземпляра <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> в поведениях операций.  
  
4.  Если найден экземпляр <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, задайте в его свойстве <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractSurrogate%2A> новый экземпляр суррогата. Если экземпляр <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> не найден, создайте новый экземпляр и задайте для элемента <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractSurrogate%2A> нового расширения новый экземпляр суррогата.  
  
5.  Наконец, добавьте это новое поведение в текущие поведения операций, как показано в примере:  
  
     [!code-csharp[C_IDataContractSurrogate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#8)]  
  
### <a name="to-use-a-surrogate-for-metadata-import"></a>Использование суррогата для импорта метаданных  
 При импорте метаданных, таких как WSDL и XSD, для генерации клиентского кода суррогат необходимо добавить в компонент, отвечающий за генерирование кода из схемы XSD, <xref:System.Runtime.Serialization.XsdDataContractImporter>. Для этого напрямую измените объект <xref:System.ServiceModel.Description.WsdlImporter>, который используется для импорта метаданных.  
  
##### <a name="to-implement-a-surrogate-for-metadata-importation"></a>Реализация суррогата для импорта метаданных  
  
1.  Импортируйте метаданные при помощи класса <xref:System.ServiceModel.Description.WsdlImporter>.  
  
2.  Чтобы проверить, определен ли объект <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>, воспользуйтесь методом <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
3.  Если метод <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> возвращает значение `false`, создайте новый объект <xref:System.Runtime.Serialization.XsdDataContractImporter> и задайте в его свойстве <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> новый экземпляр класса <xref:System.Runtime.Serialization.ImportOptions>. В противном случае используйте импортер, возвращенный параметром `out` метода <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>.  
  
4.  Если для импортера <xref:System.Runtime.Serialization.XsdDataContractImporter> не определено свойство <xref:System.Runtime.Serialization.ImportOptions>, задайте для свойства новый экземпляр класса <xref:System.Runtime.Serialization.ImportOptions>.  
  
5.  Задайте для свойства <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A> объекта <xref:System.Runtime.Serialization.ImportOptions> импортера <xref:System.Runtime.Serialization.XsdDataContractImporter> в качестве значения новый экземпляр суррогата.  
  
6.  Добавьте объект <xref:System.Runtime.Serialization.XsdDataContractImporter> в коллекцию, возвращенную свойством <xref:System.ServiceModel.Description.MetadataExporter.State%2A> объекта <xref:System.ServiceModel.Description.WsdlImporter> (унаследован от класса <xref:System.ServiceModel.Description.MetadataExporter>).  
  
7.  Используйте метод <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> объекта <xref:System.ServiceModel.Description.WsdlImporter> для импорта всех контрактов данных схемы. Во время последнего действия генерируется код из схем, загруженных при вызове суррогата.  
  
     [!code-csharp[C_IDataContractSurrogate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#9)]  
  
### <a name="to-use-a-surrogate-for-metadata-export"></a>Использование суррогата для экспорта метаданных  
 По умолчанию при экспорте метаданных из [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для службы должны быть сгенерированы как WSDL-, так и XSD-схема. Суррогат необходимо добавить в компонент, отвечающий за генерацию XSD-схемы для типов контрактов данных, <xref:System.Runtime.Serialization.XsdDataContractExporter>. Для этого используйте либо поведение, реализующее <xref:System.ServiceModel.Description.IWsdlExportExtension> для изменения <xref:System.ServiceModel.Description.WsdlExporter>, либо напрямую измените объект <xref:System.ServiceModel.Description.WsdlExporter>, который используется для экспорта метаданных.  
  
##### <a name="to-use-a-surrogate-for-metadata-export"></a>Использование суррогата для экспорта метаданных  
  
1.  Создайте новый объект <xref:System.ServiceModel.Description.WsdlExporter> или используйте параметр `wsdlExporter`, переданный методу <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A>.  
  
2.  Чтобы проверить, определен ли объект <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>, воспользуйтесь функцией <xref:System.Runtime.Serialization.XsdDataContractExporter>.  
  
3.  Если метод <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> возвращает значение `false`, создайте новый объект <xref:System.Runtime.Serialization.XsdDataContractExporter> со сгенерированными схемами XML из объекта <xref:System.ServiceModel.Description.WsdlExporter>, и добавьте его в коллекцию, возвращенную свойством <xref:System.ServiceModel.Description.MetadataExporter.State%2A> объекта <xref:System.ServiceModel.Description.WsdlExporter>. В противном случае используйте экспортер, возвращенный параметром `out` метода <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>.  
  
4.  Если для экспортера <xref:System.Runtime.Serialization.XsdDataContractExporter> не определен объект <xref:System.Runtime.Serialization.ExportOptions>, задайте для свойства <xref:System.Runtime.Serialization.XsdDataContractExporter.Options%2A> в качестве значения новый экземпляр класса <xref:System.Runtime.Serialization.ExportOptions>.  
  
5.  Задайте для свойства <xref:System.Runtime.Serialization.ExportOptions.DataContractSurrogate%2A> объекта <xref:System.Runtime.Serialization.ExportOptions> импортера <xref:System.Runtime.Serialization.XsdDataContractExporter> в качестве значения новый экземпляр суррогата. Дальнейшие шаги по экспорту метаданных остаются без изменений.  
  
     [!code-csharp[C_IDataContractSurrogate#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#10)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.IDataContractSurrogate>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.Runtime.Serialization.ImportOptions>  
 <xref:System.Runtime.Serialization.ExportOptions>  
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
