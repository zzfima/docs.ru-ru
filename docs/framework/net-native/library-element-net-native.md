---
title: <Library> Элемент (машинный код .NET)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda4f8d3819af05b022e0633d6883cca940f67e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61866867"
---
# <a name="library-element-net-native"></a>\<Библиотека > элемент (машинный код .NET)
Определяет сборку, содержащую типы и члены типов, метаданные которой доступны для отражения во время выполнения.  
  
 Элемент \<Directives>  
Элемент \<Library>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`Name`|Обязательный атрибут. Задает имя сборки. Дочерние элементы данного элемента `<Library>` определяют политику отражения среды выполнения для типов и членов типов в этой сборке.|  
  
## <a name="name-attribute"></a>Name - атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|*assembly_name*|Простое имя сборки без расширения файла. Этот атрибут соответствует свойству <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>. Например, имя сборки с именем Extensions.dll является «Extensions». Сведения об особой форме имени сборки *assembly_name* с поддержкой условного включения метаданных сборки см. в разделе "Примечания".|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Применяет политику ко всем типам в определенной сборке.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|Применяет политику ко всем типам в определенном пространстве имен.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Применяет политику для конкретного типа, например, класса или структуры.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Применяет политику к сконструированному универсальному типу. Например, элемент [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) можно использовать для определения политики для типа `List<String>`.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)|Корневой элемент файла директив среды выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Элемент [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) может иметь ноль, один или более элементов `<Library>`.  
  
 Элемент `<Library>` используется как контейнер для определения программных элементов, метаданные которых требуются во время выполнения. Этот элемент не выражают политики. Во время компиляции средства компилятора осуществляют поиск только в библиотеке, назначенной с помощью элемента `<Library>`, на наличие программных элементов, определенных его дочерними элементами. Напротив, средства компилятора проверяют все библиотеки, в том числе основные библиотеки .NET Framework, на наличие программных элементов, которые определяются дочерними элементами элемента [\<Application>](../../../docs/framework/net-native/application-element-net-native.md).  
  
 Директивы `<Library>` могут использоваться условно. Если имя `<Library>` начинается и заканчивается звездочкой (\*), `<Library>` директива действует только в том случае, если ссылку на его сборку, указанную между звездочками. Например, следующие директивы среды выполнения применяются только к сборке Utillities.dll, на которую ссылается приложение.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>См. также

- [\<Приложение > элемент](../../../docs/framework/net-native/application-element-net-native.md)
- [\<Директивы > элемент](../../../docs/framework/net-native/directives-element-net-native.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Элементы директив среды выполнения](../../../docs/framework/net-native/runtime-directive-elements.md)
