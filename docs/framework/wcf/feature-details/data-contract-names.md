---
title: Имена контрактов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], naming
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
ms.openlocfilehash: cd878452f3ec99627507334a26873a004e5b5314
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46489202"
---
# <a name="data-contract-names"></a>Имена контрактов данных

Иногда клиент и служба поддерживают разные типы. Они все равно могут передавать данные друг другу при условии, что контракты данных эквивалентны на обеих сторонах. [Эквивалентность контрактов данных](data-contract-equivalence.md) зависит от контракта данных и имена членов данных, и таким образом, система предоставляет механизм для сопоставления типов и членов с этими именами. В этом разделе описываются правила именования контрактов данных, а также инфраструктуре Windows Communication Foundation (WCF) по умолчанию при создании имен.

## <a name="basic-rules"></a>Основные правила
Ниже приведены основные правила именования контрактов данных:

- Полное имя контракта данных состоит из пространства имен и имени.

- Члены данных имеют только имена, но не имеют пространств имен.

- При обработке контрактов данных, инфраструктура WCF учитывает регистр пространства имен и имена контрактов данных и члены данных.

## <a name="data-contract-namespaces"></a>Пространства имен контракта данных
Пространство имен контракта данных принимает форму универсального кода ресурса (URI). URI может быть как абсолютным, так и относительным. По умолчанию контрактам данных определенного типа данных присваивается пространство имен из пространства имен среды CLR этого типа.

По умолчанию любое пространство имен среды CLR (в формате *Clr.Namespace*) пространство имен `http://schemas.datacontract.org/2004/07/Clr.Namespace`. Для переопределения данной настройки по умолчанию необходимо применить атрибут <xref:System.Runtime.Serialization.ContractNamespaceAttribute> ко всему модулю или всей сборке. Кроме того, для того чтобы управлять пространством имен контракта данных для каждого типа, необходимо задать свойство <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> атрибута <xref:System.Runtime.Serialization.DataContractAttribute>.

> [!NOTE]
> `http://schemas.microsoft.com/2003/10/Serialization` Пространства имен зарезервированы и не может использоваться как пространство имен контракта данных.

> [!NOTE]
> Нельзя переопределять заданное по умолчанию пространство имен в типах контрактов данных, содержащих объявления `delegate`.

## <a name="data-contract-names"></a>Имена контрактов данных
Имя контракта данных по умолчанию для данного типа является именем этого типа. Для переопределения данной настройки по умолчанию необходимо задать свойству <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> атрибута <xref:System.Runtime.Serialization.DataContractAttribute> альтернативное имя. Специальные правила для универсальных типов описаны в части "Имена контрактов данных для универсальных типов" данного раздела (см. ниже).

## <a name="data-member-names"></a>Имена членов данных
Имя члена данных по умолчанию для указанного поля или свойства является именем этого поля или свойства. Для переопределения данной настройки по умолчанию необходимо задать свойству <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> альтернативное значение.

### <a name="examples"></a>Примеры
В следующем примере показано, как переопределить заданный по умолчанию принцип именования контрактов данных и членов данных.

[!code-csharp[C_DataContractNames#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
[!code-vb[C_DataContractNames#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]

## <a name="data-contract-names-for-generic-types"></a>Имена контрактов данных для универсальных типов
Имена контрактов данных для универсальных типов определяются по специальным правилам. Эти правила позволяют избежать конфликтов имен контрактов данных, когда речь идет о двух закрытых универсальных шаблонах одного универсального типа.

По умолчанию именем контракта данных для универсального типа — имя типа, за которым следует строка «Of», следуют имена контрактов данных универсальных параметров, за которым следует *хэш* с использованием пространства имен контракта данных универсальные параметры. Хэш - это результат математической функции, действующей как "отпечаток", который однозначно определяет блок данных. Когда все универсальные параметры являются типами-примитивами, хэш не используется.

Например, см. типы в следующем примере.

[!code-csharp[C_DataContractNames#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
[!code-vb[C_DataContractNames#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]

В данном примере тип `Drawing<Square,RegularRedBrush>` имеет имя контракта данных "DrawingOfSquareRedBrush5HWGAU6h", где "5HWGAU6h" - это хэш пространств имен "urn:shapes" и "urn:default". В данном примере тип `Drawing<Square,SpecialRedBrush>` имеет имя контракта данных DrawingOfSquareRedBrushjpB5LgQ_S", где "jpB5LgQ_S" – это хэш пространств имен "urn:shapes" и "urn:special". Обратите внимание, что идентичность двух имен в случае, когда не используется хэш, приводит к конфликту имен.

## <a name="customizing-data-contract-names-for-generic-types"></a>Настройка имен контрактов данных для универсальных типов

Иногда имена контрактов данных, созданные для универсальных типов ранее описанным способом, недопустимы. Например, вы, возможно, заранее знаете, что конфликта имен не произойдет, и хотите удалить хэш. В этом случае можно использовать свойство <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> атрибута `DataContractAttribute`, чтобы указать другой способ создания имен. Вы можете использовать числа в фигурных скобках внутри свойства `Name` для ссылки на имена контрактов данных универсальных параметров. (0 относится к первому параметру, 1 - ко второму, и т. д.) Для ссылки на хэш можно использовать знак номера (#) в фигурных скобках. Каждую из этих ссылок можно использовать несколько раз или не использовать совсем.

Например, приведенный выше универсальный тип `Drawing` мог бы быть объявлен так, как показано в примере ниже.

[!code-csharp[c_DataContractNames#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
[!code-vb[c_DataContractNames#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]

В данном случае тип `Drawing<Square,RegularRedBrush>` имеет имя контракта данных "Drawing_using_RedBrush_brush_and_Square_shape". Обратите внимание, что так как в свойстве <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> имеется знак "{#}", хэш не является частью имени, и, следовательно, могут возникнуть конфликты имен данного типа; например, тип `Drawing<Square,SpecialRedBrush>` имеет точно такое же имя контракта данных.

## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.ContractNamespaceAttribute>
- [Использование контрактов данных](using-data-contracts.md)
- [Эквивалентность контрактов данных](data-contract-equivalence.md)
- [Имена контрактов данных](data-contract-names.md)
- [Управление версиями контракта данных](data-contract-versioning.md)