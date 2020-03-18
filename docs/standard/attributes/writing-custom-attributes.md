---
title: Написание настраиваемых атрибутов
ms.date: 07/17/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET Framework], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
ms.openlocfilehash: 6570c6994c0f2e6571361c3eadc73b02a55f1584
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140585"
---
# <a name="writing-custom-attributes"></a>Написание настраиваемых атрибутов
Чтобы создавать собственные атрибуты, совсем не обязательно в совершенстве овладевать множеством новых понятий. Если вы знакомы с объектно-ориентированным программированием и знаете, как создавать классы, вы уже обладаете почти всеми нужными знаниями. Настраиваемые атрибуты — это традиционные классы, прямо или косвенно наследующие от <xref:System.Attribute?displayProperty=nameWithType>. Подобно традиционным классам настраиваемые атрибуты содержат методы, хранящие и извлекающие данные.  
  
 Ниже приведены основные этапы правильно выстроенного процесса разработки классов настраиваемых атрибутов.  
  
- [Применение атрибута AttributeUsageAttribute](#applying-the-attributeusageattribute)  
  
- [Объявление класса атрибута](#declaring-the-attribute-class)  
  
- [Объявление конструкторов](#declaring-constructors)  
  
- [Объявление свойств](#declaring-properties)  
  
 В этом разделе описано каждое из этих действий. В конце приведен [пример настраиваемого атрибута](#custom-attribute-example).  
  
## <a name="applying-the-attributeusageattribute"></a>Применение атрибута AttributeUsageAttribute  
 Объявление настраиваемого атрибута начинается с <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>, что определяет некоторые ключевые характеристики класса атрибута. Например, можно указать, может ли атрибут быть унаследован другими классами, или указать элементы языка, к которым может применяться этот атрибут. В следующем фрагменте кода демонстрируется использование <xref:System.AttributeUsageAttribute>.  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 В <xref:System.AttributeUsageAttribute> есть три члена, которые важны для создания настраиваемых атрибутов: [AttributeTargets](#attributetargets-member), [Inherited](#inherited-property)и [AllowMultiple](#allowmultiple-property).  
  
### <a name="attributetargets-member"></a>Член AttributeTargets  
 В предыдущем примере использовался элемент <xref:System.AttributeTargets.All?displayProperty=nameWithType>, указывающий, что этот атрибут может применяться ко всем элементам программы. Можно также задать <xref:System.AttributeTargets.Class?displayProperty=nameWithType>, чтобы атрибут применялся только к классам, или <xref:System.AttributeTargets.Method?displayProperty=nameWithType>, чтобы атрибут применялся только к методам. Подобным образом с помощью настраиваемых атрибутов можно выделить любые элементы программы с целью их последующего описания.  
  
 Вы также можете передать несколько значений <xref:System.AttributeTargets>. В следующем фрагменте кода задается применение настраиваемого атрибута к любому классу или методу.  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
### <a name="inherited-property"></a>Свойство Inherited  
 Свойство <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> указывает, может ли атрибут быть унаследован классами, производными от класса, к которому этот атрибут применен. Это свойство принимает флаг `true` (по умолчанию) или `false`. В следующем примере в классе `MyAttribute` для свойства <xref:System.AttributeUsageAttribute.Inherited%2A> по умолчанию указано значение `true`, а в классе `YourAttribute` для свойства <xref:System.AttributeUsageAttribute.Inherited%2A> указано значение `false`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 Затем эти два атрибута применяются к методу в базовом классе `MyClass`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 Наконец, класс `YourClass` наследуется от базового класса `MyClass`. Метод `MyMethod` использует атрибут `MyAttribute`, но не `YourAttribute`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
### <a name="allowmultiple-property"></a>Свойство AllowMultiple  
 Свойство <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> указывает, можно ли применять к элементу несколько экземпляров атрибута. Если его значение равно `true`, допускается существование нескольких экземпляров. Если значение равно `false` (по умолчанию), можно использовать только один экземпляр.  
  
 В следующем примере в классе `MyAttribute` для свойства <xref:System.AttributeUsageAttribute.AllowMultiple%2A> задано значение `false`, а для `YourAttribute` — `true`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 При применении нескольких экземпляров этих атрибутов атрибут `MyAttribute` вызывает ошибку компилятора. В следующем примере кода показано правильное использование атрибута `YourAttribute` и неправильное использование атрибута `MyAttribute`.  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 Если оба свойства <xref:System.AttributeUsageAttribute.AllowMultiple%2A> и <xref:System.AttributeUsageAttribute.Inherited%2A> имеют значение `true`, то класс, наследуемый от другого класса, может наследовать атрибуты и иметь дополнительные экземпляры атрибута, применяемого в этом же дочернем классе. Если <xref:System.AttributeUsageAttribute.AllowMultiple%2A> имеет значение `false`, значения атрибутов в родительском классе будут перезаписаны новыми экземплярами того же самого атрибута в дочернем классе.  
  
## <a name="declaring-the-attribute-class"></a>Объявление класса атрибута  
 После применения <xref:System.AttributeUsageAttribute>можно начать определение характеристик атрибута. Объявление класса атрибута выглядит аналогично объявлению традиционного класса, как показано в следующем примере кода.  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 В этом определении атрибута демонстрируются следующие моменты.  
  
- Классы атрибутов должны объявляться как открытые классы.  
  
- В соответствии с соглашением имя класса атрибута должно завершаться словом **Attribute**. Это условие не обязательно, но рекомендуется для повышения удобства чтения. При применении атрибута использование слова Attribute является необязательным.  
  
- Все классы атрибутов должны прямо или косвенно наследовать от класса <xref:System.Attribute?displayProperty=nameWithType>.  
  
- В Microsoft Visual Basic все классы настраиваемых атрибутов должны иметь атрибут <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>.  
  
## <a name="declaring-constructors"></a>Объявление конструкторов  
 Атрибуты инициализируются с помощью конструкторов точно так же, как и традиционные классы. В следующем фрагменте кода показан типичный конструктор атрибута. Этот открытый конструктор получает параметр и устанавливает его значение равным переменной-члену.  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 Чтобы использовать различные сочетания значений, можно выполнить перегрузку конструктора. Если для класса настраиваемого атрибута также определяется и [свойство](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)) , при инициализации атрибута можно использовать сочетание именованных и позиционных параметров. Как правило, все обязательные параметры определяются как позиционные, а все необязательные — как именованные. В этом случае атрибут нельзя инициализировать без обязательного параметра. Все остальные параметры являются необязательными. Обратите внимание, что в Visual Basic конструкторы для классов атрибутов не могут использовать аргумент ParamArray.  
  
 В следующем примере кода показано, как атрибут, использующий приведенный выше конструктор, можно использовать с обязательными и необязательными параметрами. Предполагается, что этот атрибут имеет один обязательный логический параметр и одно необязательное строковое свойство.  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
## <a name="declaring-properties"></a>Объявление свойств  
 Если необходимо определить именованный параметр или предоставить простой способ получения значений, хранящихся в атрибуте, можно объявить [свойство](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)). Свойства атрибута следует объявлять как открытые сущности с описанием типа данных, который будет возвращен. Определите переменную, которая будет хранить значение свойства, и свяжите ее с методами **get** и **set** . В следующем примере кода показана реализация простого свойства в атрибуте.  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
## <a name="custom-attribute-example"></a>Пример настраиваемого атрибута  
 В этом разделе используются приведенные выше сведения и демонстрируется пример создания простого атрибута, содержащего данные об авторе раздела кода. Атрибут в этом примере хранит имя и уровень программиста, а также данные об изменениях, внесенных в код. Для хранения текущих сохраняемых значений в нем используются три закрытые переменные. Каждая переменная представлена открытым свойством, которое возвращает и задает значения. Наконец, в примере определяется конструктор с двумя обязательными параметрами.  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 Этот атрибут можно применять с помощью полного имени `DeveloperAttribute` или сокращенного имени `Developer` одним из следующих способов.  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 В первом примере этот атрибут применяется только с обязательными именованными параметрами, а во втором примере атрибут применяется и с обязательными, и с необязательными параметрами.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>
- [Атрибуты](../../../docs/standard/attributes/index.md)
