---
title: "Элемент &lt;Type&gt; (машинный код .NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
caps.latest.revision: 33
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 33
---
# Элемент &lt;Type&gt; (машинный код .NET)
Применяет политику выполнения для конкретного типа, например класса или структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
  
<Type Name="type_name"  
      Activate="policy_type"  
      Browse="policy_type"  
      Dynamic="policy_type"  
      Serialize="policy_type"   
      DataContractSerializer="policy_setting"  
      DataContractJsonSerializer="policy_setting"  
      XmlSerializer="policy_setting"  
      MarshalObject="policy_setting"  
      MarshalDelegate="policy_setting"  
      MarshalStructure="policy_setting" />  
  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общие правила|Обязательный атрибут. Задает имя типа.|  
|`Activate`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.|  
|`Browse`|Отражение|Необязательный атрибут. Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.|  
|`Serialize`|Сериализация|Необязательный атрибут. Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.|  
|`DataContractSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации, который использует <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> класса.|  
|`DataContractJsonSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации JSON, который использует <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> класса.|  
|`XmlSerializer`|Сериализация|Необязательный атрибут. Определяет политику для сериализации XML, который использует <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> класса.|  
|`MarshalObject`|Interop|Необязательный атрибут. Определяет политику для маршалинга ссылочных типов в среды выполнения Windows и COM.|  
|`MarshalDelegate`|Interop|Необязательный атрибут. Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.|  
|`MarshalStructure`|Interop|Необязательный атрибут. Определяет политики для маршалинга типов значений в машинный код.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|*Функция TYPE_NAME*|Имя типа. Если этот `<Type>` элемент является дочерним для элемента [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) или другого `<Type>` элемент, *type_name* может содержать имя типа без его пространства имен. В противном случае — *type_name* должен содержать полное имя типа.|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|Значение|Описание|  
|-----------|-----------------|  
|*policy_setting*|Параметр, применяемый для этого типа политики. Допустимые значения `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` и `Required All`. Дополнительные сведения см. в разделе [параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|Если содержащий тип является атрибутом, определяет политику выполнения для элементов кода, к которым применяется этот атрибут.|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|Применяет политику отражения события, относящегося к этому типу.|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|Применяет политику отражения поля, относящегося к этому типу.|  
|[<>\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|Применяет политику к типу параметра универсального типа.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Применяет политику к типу, если политика была применена для типа, представленного содержащим элементом `<Type>`.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Применяет политику отражения метода, относящегося к этому типу.|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному методу, относящемуся к этому типу.|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|Применяет политику отражения к свойству, относящемуся к этому типу.|  
|[<>\>](../../../docs/framework/net-native/subtypes-element-net-native.md)|Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.|  
|`<Type>`|Применяет политику отражения к вложенному типу.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения во время выполнения.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Применяет политику отражения ко всем типам в указанной сборке.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Применяет политику отражения ко всем типам в пространстве имен.|  
|`<Type>`|Применяет политику отражения к типу и всем его членам.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|  
  
## <a name="remarks"></a>Примечания  
 Атрибуты отражения, сериализации и взаимодействия являются необязательными. Если таковые отсутствуют, элемент `<Type>` служит в качестве контейнера, чьи дочерние типы определяют политику для отдельных элементов.  
  
 Если `<Type>` является дочерним элементом [ <> \</> \> ](../../../docs/framework/net-native/assembly-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/namespace-element-net-native.md), `<Type>`, или [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) , он переопределяет параметры политики, определенные в родительском элементе.  
  
 Элемент `<Type>` универсального типа применяет свою политику для всех экземпляров, которые не имеют собственной политики. Политика сконструированных универсальных типов определяется элементом [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) элемента.  
  
 Если тип является универсальным типом, именем помечено, символ апострофа ("") за которым следует его число универсальных параметров. Например `Name` атрибут `<Type>` элемент для <xref:System.Collections.Generic.List%601?displayProperty=fullName> класс отображается как `Name="System.Collections.Generic.List`1"".  
  
## <a name="example"></a>Пример  
 Следующий пример использует отражение для отображения сведений о поля, свойства и методы <xref:System.Collections.Generic.List%601?displayProperty=fullName> класса. Переменная `b` в примере является [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) элемента управления. Так как просто извлекаются сведения о типе, доступность метаданных определяется параметром политики `Browse`.  
  
 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]  
  
 Поскольку метаданные для <xref:System.Collections.Generic.List%601> класс не добавляются автоматически [!INCLUDE[net_native](../../../includes/net-native-md.md)] цепочка инструментов, в примере возникает ошибка отображения запрошенного элемента данных во время выполнения. Для обеспечения необходимыми метаданными, добавьте следующий элемент `<Type>` в файл директивы среды выполнения. Обратите внимание, что, поскольку мы предоставляем родительский [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) элемент, нам не требуется указать полное имя типа в `<Type>` элемента.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="*Application*" Dynamic="Required All" />  
      <Namespace Name ="System.Collections.Generic" >  
        <Type Name="List`1" Browse="Required All" />   
     </Namespace>  
   </Application>  
</Directives>  
  
```  
  
## <a name="example"></a>Пример  
 Следующий пример использует отражение для получения <xref:System.Reflection.PropertyInfo> , представляющий <xref:System.String.Chars%2A?displayProperty=fullName> свойство. Затем он использует [PropertyInfo.GetValue (объект, объект\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName> метод для извлечения значения седьмого знака в строке и для отображения всех символов в строке. Переменная `b` в примере является [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) элемента управления.  
  
 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]  
  
 Поскольку метаданные для <xref:System.String> объект недоступен, вызов [PropertyInfo.GetValue (объект, объект\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName> вызывает метод <xref:System.NullReferenceException> исключение при запуске времени при компиляции с параметром [!INCLUDE[net_native](../../../includes/net-native-md.md)] цепочки инструментов. Чтобы избежать исключений и предоставить необходимые метаданные, добавьте следующий элемент `<Type>` элемент в файл директив среды выполнения:  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
    <Type Name="System.String" Dynamic="Required Public"/> -->  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>См. также  
 [Ссылка на файл конфигурации директив (rd.xml) среды выполнения](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Параметры политики директив среды выполнения](../../../docs/framework/net-native/runtime-directive-policy-settings.md)