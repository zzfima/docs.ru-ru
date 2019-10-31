---
title: Элемент <Property> (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: b9bc89804a872dddf1a56c2a3dadc9c3df4f5fd1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128215"
---
# <a name="property-element-net-native"></a>Элемент > свойства \<(.NET Native)
Применяет политику отражения среды выполнения к свойству.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Тип атрибута|Описание|  
|---------------|--------------------|-----------------|  
|`Name`|Общее|Обязательный атрибут. Задает имя свойства.|  
|`Browse`|Отражение|Необязательный атрибут. Определяет запрос для получения сведений о свойстве или перечисляет свойство, но не включает динамический доступ во время выполнения.|  
|`Dynamic`|Отражение|Необязательный атрибут. Управляет доступом среды выполнения к свойству для включения динамического программирования. Эта политика гарантирует, что свойство можно задать или получить динамически во время выполнения.|  
|`Serialize`|Сериализация|Необязательный атрибут. Управляет доступом среды выполнения к свойству, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как сериализатор Newtonsoft JSON или для привязки данных.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|значения|Описание|  
|-----------|-----------------|  
|*method_name*|Имя свойства. Тип свойства определяется родительским элементом [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).|  
  
## <a name="all-other-attributes"></a>Все остальные атрибуты  
  
|значения|Описание|  
|-----------|-----------------|  
|*policy_setting*|Параметр, применяемый к этому типу политики для свойства. Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`. Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|Применяет политику отражения к типу и всем его членам.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Применяет политику отражения к сконструированному универсальному типу и всем его членам.|  
  
## <a name="remarks"></a>Заметки  
 Если политика свойства не определена явно, оно наследует политику среды выполнения своего родительского элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере используется отражение для создания экземпляров объекта `Book` и отображения значений его свойств. Исходный файл default.rd.xml для проекта выглядит следующим образом:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 Файл применяет значение `All` к политике `Activate` для класса `Book`, который предоставляет доступ к конструкторам класса через отражение. Политика `Browse` для класса `Book` наследуется от его родительского пространства имен. Это свойство имеет значение `Required Public`, что делает метаданные доступными во время выполнения.  
  
 Ниже приведен исходный код для этого примера. Переменная `outputBlock` представляет элемент управления <xref:Windows.UI.Xaml.Controls.TextBlock>.  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 Тем не менее компиляция и выполнение этого примера создает исключение [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Несмотря на то, что мы уже сделали метаданные для типа `Book` доступными, нам не удалось обеспечить динамический доступ к реализациям свойств считывания. Эту ошибку можно исправить одним из двух способов:  
  
- определив политику `Dynamic` для типа `Book` в его элементе [\<Type>](type-element-net-native.md);  
  
- добавив вложенный элемент [\<Property>](property-element-net-native.md) для каждого свойства, считывание которого необходимо вызвать, как это делает следующий файл default.rd.xml.  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a>См. также

- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](runtime-directive-elements.md)
- [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md)
