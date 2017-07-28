---
title: "Имена контрактов данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "контракты данных [WCF], именование"
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# Имена контрактов данных
Иногда клиент и служба поддерживают разные типы.Они все равно могут передавать данные друг другу при условии, что контракты данных эквивалентны на обеих сторонах.[Эквивалентность контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md) основана на именах контракта данных и члена данных, следовательно, система предоставляет механизм для сопоставления типов и членов этим именам.В этом разделе поясняются правила именования контрактов данных и описывается поведение по умолчанию инфраструктуры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] при создании имен.  
  
## Основные правила  
 Ниже приведены основные правила именования контрактов данных:  
  
-   Полное имя контракта данных состоит из пространства имен и имени.  
  
-   Члены данных имеют только имена, но не имеют пространств имен.  
  
-   При обработке контрактов данных инфраструктура [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] учитывает регистр пространства имен и имен контрактов данных и членов данных.  
  
## Пространства имен контракта данных  
 Пространство имен контракта данных принимает форму универсального кода ресурса \(URI\).URI может быть как абсолютным, так и относительным.По умолчанию контрактам данных определенного типа данных присваивается пространство имен из пространства имен среды CLR этого типа.  
  
 По умолчанию любое пространство имен среды CLR \(в формате *Clr.Namespace*\) сопоставляется с пространством имен "http:\/\/schemas.datacontract.org\/2004\/07\/Clr.Namespace".Для переопределения данной настройки по умолчанию необходимо применить атрибут <xref:System.Runtime.Serialization.ContractNamespaceAttribute> ко всему модулю или всей сборке.Кроме того, для того чтобы управлять пространством имен контракта данных для каждого типа, необходимо задать свойство <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> атрибута <xref:System.Runtime.Serialization.DataContractAttribute>.  
  
> [!NOTE]
>  Пространство имен "http:\/\/schemas.microsoft.com\/2003\/10\/Serialization" зарезервировано, следовательно, его невозможно использовать в качестве пространства имен контракта данных.  
  
> [!NOTE]
>  Нельзя переопределять заданное по умолчанию пространство имен в типах контрактов данных, содержащих объявления `delegate`.  
  
## Имена контрактов данных  
 Имя контракта данных по умолчанию для данного типа является именем этого типа.Для переопределения данной настройки по умолчанию необходимо задать свойству <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> атрибута <xref:System.Runtime.Serialization.DataContractAttribute> альтернативное имя.Специальные правила для универсальных типов описаны в части "Имена контрактов данных для универсальных типов" данного раздела \(см. ниже\).  
  
## Имена членов данных  
 Имя члена данных по умолчанию для указанного поля или свойства является именем этого поля или свойства.Для переопределения данной настройки по умолчанию необходимо задать свойству <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> альтернативное значение.  
  
### Примеры  
 В следующем примере показано, как переопределить заданный по умолчанию принцип именования контрактов данных и членов данных.  
  
 [!code-csharp[C_DataContractNames#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
 [!code-vb[C_DataContractNames#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]  
  
## Имена контрактов данных для универсальных типов  
 Имена контрактов данных для универсальных типов определяются по специальным правилам.Эти правила позволяют избежать конфликтов имен контрактов данных, когда речь идет о двух закрытых универсальных шаблонах одного универсального типа.  
  
 По умолчанию именем контракта данных для универсального типа является имя этого типа и строки "Of", за которыми следуют имена контрактов данных универсальных параметров и *хэш*, вычисляемый с помощью пространств имен контрактов данных универсальных параметров.Хэш — это результат математической функции, действующей как "отпечаток", который однозначно определяет блок данных.Когда все универсальные параметры являются типами\-примитивами, хэш не используется.  
  
 Например, см. типы в следующем примере.  
  
 [!code-csharp[C_DataContractNames#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
 [!code-vb[C_DataContractNames#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]  
  
 В данном примере тип `Drawing<Square,RegularRedBrush>` имеет имя контракта данных "DrawingOfSquareRedBrush5HWGAU6h", где "5HWGAU6h" — это хэш пространств имен "urn:shapes" и "urn:default".В данном примере тип `Drawing<Square,SpecialRedBrush>` имеет имя контракта данных DrawingOfSquareRedBrushjpB5LgQ\_S", где "jpB5LgQ\_S" – это хэш пространств имен "urn:shapes" и "urn:special".Обратите внимание, что идентичность двух имен в случае, когда не используется хэш, приводит к конфликту имен.  
  
## Настройка имен контрактов данных для универсальных типов  
 Иногда имена контрактов данных, созданные для универсальных типов ранее описанным способом, недопустимы.Например, вы, возможно, заранее знаете, что конфликта имен не произойдет, и хотите удалить хэш.В этом случае можно использовать свойство <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> атрибута `DataContractAttribute`, чтобы указать другой способ создания имен.Вы можете использовать числа в фигурных скобках внутри свойства `Name` для ссылки на имена контрактов данных универсальных параметров.\(0 относится к первому параметру, 1 — ко второму, и т. д.\) Для ссылки на хэш можно использовать знак номера \(\#\) в фигурных скобках.Каждую из этих ссылок можно использовать несколько раз или не использовать совсем.  
  
 Например, приведенный выше универсальный тип `Drawing` мог бы быть объявлен так, как показано в примере ниже.  
  
 [!code-csharp[c_DataContractNames#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
 [!code-vb[c_DataContractNames#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]  
  
 В данном случае тип `Drawing<Square,RegularRedBrush>` имеет имя контракта данных "Drawing\_using\_RedBrush\_brush\_and\_Square\_shape".Обратите внимание, что так как в свойстве <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> имеется знак "{\#}", хэш не является частью имени, и, следовательно, могут возникнуть конфликты имен данного типа; например, тип `Drawing<Square,SpecialRedBrush>` имеет точно такое же имя контракта данных.  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 <xref:System.Runtime.Serialization.ContractNamespaceAttribute>   
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Эквивалентность контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)   
 [Data Contract Names](../../../../docs/framework/wcf/feature-details/data-contract-names.md)   
 [Управление версиями контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)