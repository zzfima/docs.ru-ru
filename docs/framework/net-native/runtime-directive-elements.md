---
title: Элементы директив среды выполнения
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128172"
---
# <a name="runtime-directive-elements"></a>Элементы директив среды выполнения
Формат файла директив (rd.xml) среды выполнения поддерживает следующие элементы директивы среды выполнения. Иерархическое представление см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [\<Application>](application-element-net-native.md)  
 Применяется политика отражения среды выполнения для всех типов, используемых в приложении и служит в качестве контейнера для приложения типы и члены типов, метаданные которого доступны для отражения во время выполнения. Это дочерний элемент для элемента [\<Directives>](directives-element-net-native.md).  
  
 [\<Assembly>](assembly-element-net-native.md)  
 Применяет политику среды выполнения ко всем типам в сборке. Это дочерний элемент элементов [\<Application>](application-element-net-native.md) и [\<Library>](library-element-net-native.md).  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 Если содержащая директива [\<Type>](type-element-net-native.md) является атрибутом, применяет политику среды выполнения к элементам кода, к которым применяется атрибут.  
  
 [\<Directives>](directives-element-net-native.md)  
 Корневой элемент в каждом файле директив среды выполнения для .NET Native. Его дочерними элементами являются элементы [\<Application>](application-element-net-native.md) и [\<Library>](library-element-net-native.md).  
  
 [\<Event>](event-element-net-native.md)  
 Применяет политику среды выполнения к событию. Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Field>](field-element-net-native.md)  
 Применяет политику среды выполнения к полю. Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 Применяет политику среды выполнения к параметру типа универсального типа или метода.  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 Применяет политику среды выполнения к типу, если политика была применена к содержащему типу или методу.  
  
 [\<Library>](library-element-net-native.md)  
 Применяет политику среды выполнения ко всем типам в сборке. Это дочерний элемент элементов [\<Application>](application-element-net-native.md) и [\<Library>](library-element-net-native.md).  
  
 [\<Method>](method-element-net-native.md)  
 Применяет политику среды выполнения к методу. Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 Применяет политику среды выполнения к сконструированному универсальному методу. Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Namespace>](namespace-element-net-native.md)  
 Применяет политику среды выполнения ко всем типам в пространстве имен.  
  
 [\<Parameter>](parameter-element-net-native.md)  
 Применяет политику среды выполнения к типу аргумента, переданного методу.  
  
 [\<Property>](property-element-net-native.md)  
 Применяет политику среды выполнения к свойству. Это дочерний элемент элементов [\<Type>](type-element-net-native.md) и [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.  
  
 [\<Type>](type-element-net-native.md)  
 Применяет политику среды выполнения к типу.  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 Применяет политику среды выполнения к сконструированному универсальному типу.  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 Применяет политику среды выполнения к типу, представленному аргументом <xref:System.Type>, переданным методу.  
  
## <a name="see-also"></a>См. также

- [Справочник по конфигурационному файлу rd.xml](runtime-directives-rd-xml-configuration-file-reference.md)
