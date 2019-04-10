---
title: Типы перечислений в контрактах данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], enumeration types
ms.assetid: b5d694da-68cb-4b74-a5fb-75108a68ec3b
ms.openlocfilehash: 1837a3630424ff2a9ee4a84e9ed63f44a06bbecf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309645"
---
# <a name="enumeration-types-in-data-contracts"></a>Типы перечислений в контрактах данных
Перечисления могут быть выражены в модели контракта данных. В этом разделе представлено несколько примеров, иллюстрирующих использование модели программирования.  
  
## <a name="enumeration-basics"></a>Основные сведения о перечислениях  
 Одним из способов использования типов перечисления в модели контрактов данных является применение к типу атрибута <xref:System.Runtime.Serialization.DataContractAttribute>. Затем необходимо применить атрибут <xref:System.Runtime.Serialization.EnumMemberAttribute> к каждому члену, включаемому в контракт данных.  
  
 В следующем примере показаны два класса. Первый использует перечисление, а второй - определяет его.  
  
 [!code-csharp[c_DataContractEnumerations#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#1)]
 [!code-vb[c_DataContractEnumerations#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#1)]  
  
 Экземпляр класса `Car` можно отправить или получить, только если полю `condition` задано значение `New`, `Used` или `Rental`. Если `condition` имеет значение `Broken` или `Stolen`, создается исключение <xref:System.Runtime.Serialization.SerializationException>.  
  
 Свойства <xref:System.Runtime.Serialization.DataContractAttribute> (<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> и <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>) можно использовать в контрактах данных перечисления как обычно.  
  
### <a name="enumeration-member-values"></a>Значения членов перечисления  
 Как правило, контракт данных содержит имена членов перечисления, а не числовые значения. Тем не менее при использовании модели контракта данных, если получающей стороной является клиент WCF, экспортированной схеме сохраняет числовые значения. Обратите внимание, что это не так при использовании [с помощью класса XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).  
  
 В предыдущем примере, если `condition` задано значение `Used` и данные сериализуются в формат XML, получается XML-код `<condition>Used</condition>`, а не `<condition>1</condition>`. Поэтому следующий контракт данных эквивалентен контракту данных `CarConditionEnum`.  
  
 [!code-csharp[c_DataContractEnumerations#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#2)]
 [!code-vb[c_DataContractEnumerations#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#2)]  
  
 Например, на отправляющей стороне можно использовать `CarConditionEnum`, а `CarConditionWithNumbers` - на получающей. Хотя отправляющая сторона использует для `Used` значение "1", а получающая сторона - "20", представлением XML для обеих сторон является `<condition>Used</condition>`.  
  
 Для включения в контракт данных необходимо применить атрибут <xref:System.Runtime.Serialization.EnumMemberAttribute>. В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] всегда можно применить к перечислению специальное значение 0 (нуль), которое, кроме того, является значением по умолчанию для любого перечисления. Однако даже это специальное нулевое значение не удастся сериализовать, если оно не помечено атрибутом <xref:System.Runtime.Serialization.EnumMemberAttribute>.  
  
 Существует два исключения из этого правила.  
  
-   Во-первых, перечисления флагов (см. далее в этом разделе).  
  
-   Во-вторых, члены данных перечисления, свойству <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> которых задано значение `false` (в этом случае перечисление с нулевым значением исключается из сериализованных данных).  
  
### <a name="customizing-enumeration-member-values"></a>Настройка значений членов перечисления  
 Настройка значения членов перечисления, входящего в состав контракта данных, осуществляется с помощью свойства <xref:System.Runtime.Serialization.EnumMemberAttribute.Value%2A> атрибута <xref:System.Runtime.Serialization.EnumMemberAttribute>.  
  
 Так, следующий контракт данных также эквивалентен контракту данных перечисления `CarConditionEnum`.  
  
 [!code-csharp[c_DataContractEnumerations#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#3)]
 [!code-vb[c_DataContractEnumerations#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#3)]  
  
 При сериализации значение `PreviouslyOwned` имеет представление XML `<condition>Used</condition>`.  
  
## <a name="simple-enumerations"></a>Простые перечисления  
 Кроме того, можно сериализовать типы перечислений, к которым не был применен атрибут <xref:System.Runtime.Serialization.DataContractAttribute>. Эти типы перечислений обрабатываются точно так же, как описано выше, за исключением того, что каждый член (к которому не применяется атрибут <xref:System.NonSerializedAttribute>) обрабатывается, как если бы атрибут <xref:System.Runtime.Serialization.EnumMemberAttribute> применялся. Например, следующее перечисление неявно содержит контракт данных, эквивалентный контракту, описанному в примере `CarConditionEnum`.  
  
 [!code-csharp[c_DataContractEnumerations#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#6)]
 [!code-vb[c_DataContractEnumerations#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#6)]  
  
 Если не нужно настраивать имя и пространство имен контракта данных перечисления, а также значения членов перечисления, можно использовать простые перечисления.  
  
#### <a name="notes-on-simple-enumerations"></a>Замечания о простых перечислениях  
 Применение атрибута <xref:System.Runtime.Serialization.EnumMemberAttribute> к простым перечислениям не дает результата.  
  
 Не имеет значения, применяется ли атрибут <xref:System.SerializableAttribute> к перечислению.  
  
 Тот факт, что класс <xref:System.Runtime.Serialization.DataContractSerializer> учитывает атрибут <xref:System.NonSerializedAttribute>, применимый к членам перечисления, отличает его от поведения классов <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. Оба сериализатора игнорируют атрибут <xref:System.NonSerializedAttribute>.  
  
## <a name="flag-enumerations"></a>Перечисления флагов  
 К перечислениям можно применить атрибут <xref:System.FlagsAttribute>. В этом случае можно организовать одновременную отправку или получение списка нулевых и других значений перечисления.  
  
 Для этого нужно применить атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к перечислению флагов, а затем пометить атрибутом <xref:System.Runtime.Serialization.EnumMemberAttribute> все члены, являющиеся степенями двух. Обратите внимание, что использование перечисления флагов возможно только в том случае, если имеется непрерывная последовательность степеней двух (например, 1, 2, 4, 8, 16, 32, 64).  
  
 Чтобы отправить значение перечисления флага, нужно выполнить следующие действия.  
  
1. Попытайтесь найти член перечисления (с примененным атрибутом <xref:System.Runtime.Serialization.EnumMemberAttribute>), который сопоставляется числовому значению. Если удается найти этот член, отправьте список, содержащий только этот член.  
  
2. Попытайтесь представить числовое значение в виде суммы так, чтобы имелись члены перечисления (каждый с примененным атрибутом <xref:System.Runtime.Serialization.EnumMemberAttribute>), сопоставляемые каждой части этой суммы. Отправьте список всех этих членов. Обратите внимание, что *жадный алгоритм* используется для нахождения такой суммы, и таким образом, нет никакой гарантии, что такая Сумма находится в том случае, даже если он имеется. Чтобы избежать этой проблемы, нужно убедиться, что числовые значения членов перечисления представляют собой степени двух.  
  
3. Если не удается выполнить предыдущие два шага и числовое значение ненулевое, создайте исключение <xref:System.Runtime.Serialization.SerializationException>. Если числовое значение равно нулю, отправьте пустой список.  
  
### <a name="example"></a>Пример  
 Следующий пример перечисления можно использовать в операции флага.  
  
 [!code-csharp[c_DataContractEnumerations#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#4)]
 [!code-vb[c_DataContractEnumerations#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#4)]  
  
 Следующие значения из примера сериализуются, как указано.  
  
 [!code-csharp[c_DataContractEnumerations#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#5)]
 [!code-vb[c_DataContractEnumerations#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#5)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [Задание передачи данных в контрактах служб](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)
