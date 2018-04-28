---
title: Управление версиями контракта данных
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- versioning [WCF], data contracts
- versioning [WCF]
- data contracts [WCF], versioning
ms.assetid: 4a0700cb-5f5f-4137-8705-3a3ecf06461f
caps.latest.revision: 35
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f232cb1cf98fe01aa0542c2a4b459fb7fc7b5089
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="data-contract-versioning"></a>Управление версиями контракта данных
По мере развития приложений может возникнуть необходимость в изменении контрактов данных, используемых службами. В данном разделе описано, как создавать версии контрактов данных. В этом разделе описываются механизмы создания версий контрактов данных. Полный обзор и руководство по управлению версиями см. в разделе [рекомендации: управление версиями контракта данных](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).  
  
## <a name="breaking-vs-nonbreaking-changes"></a>Сравнение критических и некритических изменений  
 Изменения в контрактах данных могут быть критическими и некритическими. Когда изменение контракта данных не является критическим, приложение, использующее старую версию контракта, может взаимодействовать с приложением, использующим новую версию, и приложение, использующее новую версию контракта, может взаимодействовать с приложением, использующим старую версию. Напротив, критическое изменение исключает взаимодействие в одном или обоих направлениях.  
  
 Любые изменения типа, не влияющие на способ его передачи и приема, являются некритическими. Такие изменения не изменяют контракт данных, они изменяют только базовый тип. Например, изменение имени поля будет некритическим, если затем задать для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> имя из старой версии. В следующем коде показана версия 1 контракта данных.  
  
 [!code-csharp[C_DataContractVersioning#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#1)]
 [!code-vb[C_DataContractVersioning#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#1)]  
  
 В следующем коде показано некритическое изменение.  
  
 [!code-csharp[C_DataContractVersioning#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#2)]
 [!code-vb[C_DataContractVersioning#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#2)]  
  
 Некоторые изменения влияют на передаваемые данные, но могут быть как критическими, так и некритическими. Указанные ниже изменения всегда критические.  
  
-   Изменение значения <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> или <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> контракта данных.  
  
-   Изменение порядка членов данных с помощью свойства <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
-   Переименование члена данных.  
  
-   Изменение контракта данных члена данных. Например, изменение типа члена данных с целого числа на строку или с типа, имеющего контракт данных с именем "Заказчик" на тип, имеющий контракт данных с именем "Личность".  
  
 Возможны также указанные ниже изменения.  
  
## <a name="adding-and-removing-data-members"></a>Добавление и удаление членов данных  
 В большинстве случаев добавление или удаление члена данных не является критическим изменением, если только не требуется строгая достоверность схемы (новые экземпляры проверяются по старой схеме).  
  
 Когда тип с дополнительным полем десериализуется в тип с отсутствующим полем, дополнительная информация игнорируется. (Может быть также сохранены для целей кругового обращения; Дополнительные сведения, см. [прямой совместимостью контракты данных](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)).  
  
 Когда тип с отсутствующим полем десериализуется в тип с дополнительным полем, для дополнительного поля сохраняется значение по умолчанию, обычно ноль или `null`. (Значение по умолчанию может быть изменено; Дополнительные сведения см. в разделе [обратных вызовов независимой от версий сериализации](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md).)  
  
 Например, можно использовать класс `CarV1` в клиенте и класс `CarV2` в службе или можно использовать класс `CarV1` в службе и класс `CarV2` в клиенте.  
  
 [!code-csharp[C_DataContractVersioning#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#3)]
 [!code-vb[C_DataContractVersioning#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#3)]  
  
 Конечная точка версии 2 успешно передала данные конечной точке версии 1. В результате сериализации версии 2 контракта данных `Car` получается код XML, аналогичный приведенному ниже.  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
    <HorsePower>300</HorsePower>  
</Car>  
```  
  
 Механизм десериализации в V1 не находит соответствующего члена данных для поля `HorsePower` и отбрасывает эти данные.  
  
 Конечная точка версии 1 также может передать данные конечной точке версии 2. В результате сериализации версии 1 контракта данных `Car` получается код XML, аналогичный приведенному ниже.  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
</Car>  
```  
  
 Десериализатор версии 2 не знает, какое значение следует присвоить полю `HorsePower`, поскольку во входящем коде XML нет соответствующих данных. В результате этому полю присваивается значение по умолчанию "0".  
  
## <a name="required-data-members"></a>Обязательные члены данных  
 Член данных можно пометить как обязательный, задав для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> значение `true`. В случае отсутствия во время десериализации обязательных данных вместо присваивания этому члену данных значения по умолчанию генерируется исключение.  
  
 Добавление обязательного члена данных - это критическое изменение. То есть, новый тип можно передавать на конечные точки старого типа, но не наоборот. Удаление члена данных, помеченного в старой версии как обязательный, также является критическим изменением.  
  
 Изменение значения свойства <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> с `true` на `false` не является критическим изменением, а изменение со значения `false` на значение `true` может быть критическим, если в какой-либо предыдущей версии этого типа соответствующий член данных отсутствует.  
  
> [!NOTE]
>  Даже если для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> задано значение `true`, входящие данные могут иметь значение "null" или ноль, и тип должен быть готов к обработке такой ситуации. Не используйте значение <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> в качестве механизма защиты от неправильных входных данных.  
  
## <a name="omitted-default-values"></a>Опущенные значения по умолчанию  
 Это возможно (хотя и не рекомендуется) для установки `EmitDefaultValue` атрибута DataMemberAttribute на `false`, как описано в [значения по умолчанию членов данных](../../../../docs/framework/wcf/feature-details/data-member-default-values.md). Если задано значение `false`, член данных не передается, если для него установлено значение по умолчанию (обычно "null" или ноль). Это не совместимо с обязательными членами данных в различных версиях по двум причинам.  
  
-   Контракт данных, содержащий член данных, обязательный в одной версии, не может принимать данные по умолчанию ("null" или ноль) из другой версии, в которой для свойства `EmitDefaultValue` этого члена данных задано значение `false`.  
  
-   Обязательный член данных, для свойства `EmitDefaultValue` которого задано значение `false`, не может использоваться для сериализации его значения по умолчанию ("null" или ноль), но может получить такое значение при десериализации. Это создает проблему при круговой передаче (данные можно считать, но эти же данные невозможно потом записать). Поэтому если в одной версии для свойства `IsRequired` задано значение `true` и для свойства `EmitDefaultValue` задано значение `false`, это же сочетание должно применяться во всех остальных версиях, чтобы ни одна из версий контракта данных не могла создать значение, которое не сможет пройти круговую передачу.  
  
## <a name="schema-considerations"></a>Замечания по схемам  
 Описание схемы, создаваемой для типов контрактов данных см. в разделе [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
 Схема, которую [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] создает для типов контракта данных, не поддерживает управление версиями. Это означает, что схема, экспортированная из определенной версии типа, содержит только те члены данных, которые присутствуют в этой версии. Реализация интерфейса <xref:System.Runtime.Serialization.IExtensibleDataObject> не изменяет схему для типа.  
  
 По умолчанию члены данных экспортируются в схему как необязательные элементы. То есть значение `minOccurs` (XML-атрибут) равно 0. Необходимые члены данных экспортируются, если параметр `minOccurs` имеет значение 1.  
  
 Многие изменения, считающиеся некритическими, на самом деле являются критическими, если требуется строгое соответствие схеме. В предыдущем примере экземпляр `CarV1`, содержащий только элемент `Model`, пройдет проверку по схеме `CarV2` (содержащую элементы `Model` и `Horsepower`, оба необязательные). Однако обратное неверно: экземпляр `CarV2` не пройдет проверку по схеме `CarV1`.  
  
 Следует учитывать возможность круговой передачи. Дополнительные сведения см. в подразделе «Замечания по схемам» [прямой совместимостью контракты данных](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
### <a name="other-permitted-changes"></a>Другие разрешенные изменения  
 Реализация интерфейса <xref:System.Runtime.Serialization.IExtensibleDataObject> является некритическим изменением. Однако для версий типа, предшествующих версии, в которой был реализован интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject>, поддержка кругового пути отсутствует. Дополнительные сведения о создании контрактов данных, обладающих прямой совместимостью, см. в разделе [Контракты данных, совместимые с любыми будущими изменениями](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
## <a name="enumerations"></a>Перечисления  
 Добавление или удаление члена перечисления - это критическое изменение. Изменение имени члена перечисления также является критическим изменением, за исключением случая, когда с помощью атрибута `EnumMemberAtttribute` имя контракта оставлено таким же, как и в старой версии. Дополнительные сведения см. в разделе [типы перечислений в контрактах данных](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).  
  
## <a name="collections"></a>Коллекции  
 Большинство изменений коллекций являются некритическими, так как в модели контракта данных большинство типов коллекции взаимозаменяемы. Однако преобразование стандартной коллекции в настраиваемую или наоборот является критическим изменением. Итак, изменение параметров настройки коллекции является весьма важным. Сюда относится изменение ее имени контракта данных и пространства имен, имени повторяющегося элемента, имени ключевого элемента и имени элемента значения. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] настройке коллекции см. в разделе [типы коллекций в контрактах данных](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).  
Конечно, изменение контракта данных содержимого коллекции (например, переход со списка целых чисел на список строк) является важным изменением.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>  
 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>  
 <xref:System.Runtime.Serialization.SerializationException>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 [Обратные вызовы сериализации, независимые от версий](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)  
 [Рекомендации. Управление версиями контракта данных](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Эквивалентность контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [Контракты данных, совместимые с любыми будущими изменениями](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)
