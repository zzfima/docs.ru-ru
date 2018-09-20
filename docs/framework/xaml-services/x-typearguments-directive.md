---
title: Директива x:TypeArguments
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 28eda94914125f2c5849a471671c8e283475c82c
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46321396"
---
# <a name="xtypearguments-directive"></a>Директива x:TypeArguments
Передает аргументы типов ограничений универсального в конструктор универсального типа.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`object`|Объявление элемента объекта типа XAML, который реализуется универсальным типом среды CLR. Если `object` ссылается на тип XAML, не из пространства имен XAML по умолчанию, `object` требует префикса для указания пространства имен XAML где `object` существует.|  
|`typeString`|Строка, которая объявляет один или несколько XAML тип имена как строки, которая предоставляет аргументы типа для универсального типа среды CLR. См. в разделе "Примечания" для заметки дополнительный синтаксис.|  
  
## <a name="remarks"></a>Примечания  
 В большинстве случаев типы XAML, которые используются как элемент в `typeString` имеют префикс строки. Типичные виды CLR универсальные ограничения (например, <xref:System.Int32> и <xref:System.String>) из библиотеки базовых классов среды CLR. Эти библиотеки не пространства имен XAML может выполняться с обычной по умолчанию конкретной платформы и поэтому требуют сопоставления префиксов для использования XAML.  
  
 Можно указать более одного имени типа XAML, используя запятую в качестве разделителя.  
  
 Универсальные ограничения сами используют универсальные типы, аргументы типа вложенного ограничения могут быть включены в скобки ().  
  
 Обратите внимание, что это определение `x:TypeArguments` относится к службами XAML .NET Framework и с помощью резервирования CLR. Определение языка можно найти в [ \[MS-XAML\] разделе 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Примеры использования  
 В этих примерах предполагается, что объявлены следующие определения пространства имен XAML:  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>Список\<строка >  
 `<scg:List x:TypeArguments="sys:String" ...>` Создает новый экземпляр <xref:System.Collections.Generic.List%601> с <xref:System.String> аргумент типа.  
  
### <a name="dictionarystringstring"></a>Словарь\<String, String >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` Создает новый экземпляр <xref:System.Collections.Generic.Dictionary%602> с двумя <xref:System.String> аргументы типа.  
  
### <a name="queuekeyvaluepairstringstring"></a>Очередь < KeyValuePair\<String, String >>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` Создает новый экземпляр <xref:System.Collections.Generic.Queue%601> , имеет ограничение <xref:System.Collections.Generic.KeyValuePair%602> с аргументами типа внутреннее ограничение <xref:System.String> и <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Данные об использовании универсального XAML XAML 2006 и WPF  
 Для использования XAML 2006 и XAML, который используется для приложений WPF, действуют следующие ограничения для `x:TypeArguments` и их использование универсального типа из XAML в целом:  
  
-   Только корневой элемент файла XAML может поддерживать универсального использования XAML, который ссылается на универсальный тип.  
  
-   Корневой элемент необходимо сопоставить с хотя бы один тип аргумента универсального типа. Например, <xref:System.Windows.Navigation.PageFunction%601>. Функции страницы являются основным сценарием для поддержки универсального использования XAML в WPF.  
  
-   Корневой элемент XAML объектного элемента для универсального также необходимо объявить в разделяемый класс с помощью `x:Class`. Это справедливо, даже если определение WPF действие при сборке.  
  
-   `x:TypeArguments` не может ссылаться на вложенные универсальные ограничения.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 или XAML 2006 без WPF 3.0 или WPF 3.5 зависимостей  
 В службах XAML .NET Framework для XAML 2006 или XAML 2009 относящихся к WPF ограничения для универсального использования XAML освобождаются. Можно создать экземпляр универсального объектного элемента в любом положении в разметке XAML, которые может поддерживать резервного типа системы и объект модели.  
  
 При использовании XAML 2009 вместо сопоставление среды CLR базовые типы для получения типов XAML для общих примитивов языка, можно использовать [встроенные типы для общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) сведения в виде элементов `typeString`. Например, можно объявить следующее (префикс сопоставления не отображаются, но x — это пространство имен XAML языка XAML для XAML 2009 г.):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 В WPF и при нацеливании на [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать возможности XAML 2009 вместе с `x:TypeArguments` , но только для свободного XAML (XAML, который не является компилированной разметкой). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009. Если вы необходимости компиляции разметки XAML, нужно следовать ограничениям, указанным в разделе «XAML 2006 и универсального XAML способы использования WPF».  
  
## <a name="see-also"></a>См. также  
 [Директива x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Расширение разметки x:Type](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Встроенные типы для общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [Универсальные шаблоны в XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)
