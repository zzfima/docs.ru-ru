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
ms.openlocfilehash: a2a960870d368e57272b3368e69eb38ebbe2ba5d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053719"
---
# <a name="xtypearguments-directive"></a>Директива x:TypeArguments
Передает ограничивающие аргументы типа универсального класса в конструктор универсального типа.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`object`|Объявление объектного элемента типа XAML, который поддерживается универсальным типом CLR. Если `object` ссылается на тип XAML, который не относится к пространству имен XAML по `object` умолчанию, требуется префикс, указывающий пространство `object` имен XAML, где существует.|  
|`typeString`|Строка, объявляющая одно или несколько имен типов XAML в виде строк, которые предоставляют аргументы типа для универсального типа CLR. Дополнительные сведения о синтаксисе см. в разделе Примечания.|  
  
## <a name="remarks"></a>Примечания  
 В большинстве случаев типы XAML, используемые в качестве информационного элемента в `typeString` строке, являются префиксами. Типичные типы универсальных ограничений CLR (например, <xref:System.Int32> и <xref:System.String>) поступают из библиотек базовых классов среды CLR. Эти библиотеки не сопоставляются с типичными пространствами имен XAML по умолчанию для конкретной платформы, поэтому для использования XAML требуется сопоставление префикса.  
  
 Можно указать несколько имен типов XAML, используя разделитель-запятую.  
  
 Если универсальные ограничения сами по себе используют универсальные типы, аргументы типа вложенного ограничения могут содержаться в круглых скобках ().  
  
 Обратите внимание, что `x:TypeArguments` это определение относится только к .NET Framework службам XAML и использованию резервного копирования среды CLR. Определение уровня языка можно найти в [ \[разделе 5.3.11 в MS-XAML\] ](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="usage-examples"></a>Примеры использования  
 В этих примерах предполагается, что объявляются следующие определения пространства имен XAML:  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a>>\<Строки списка  
 `<scg:List x:TypeArguments="sys:String" ...>`создает новый <xref:System.Collections.Generic.List%601> объект <xref:System.String> с аргументом типа.  
  
### <a name="dictionarystringstring"></a>Строка\<словаря, строка >  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`создает новый <xref:System.Collections.Generic.Dictionary%602> экземпляр с двумя <xref:System.String> аргументами типа.  
  
### <a name="queuekeyvaluepairstringstring"></a>Queue < строка\<KeyValuePair, строка > >  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`создает новый <xref:System.Collections.Generic.Queue%601> объект, имеющий <xref:System.Collections.Generic.KeyValuePair%602> ограничение с аргументами <xref:System.String> типа внутреннего ограничения и <xref:System.String>.  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a>Общие сведения об использовании XAML в XAML 2006 и WPF  
 Для использования XAML 2006 и XAML, используемого для приложений WPF, в целом существуют `x:TypeArguments` следующие ограничения на использование универсального типа из XAML.  
  
- Только корневой элемент файла XAML может поддерживать универсальное использование XAML, которое ссылается на универсальный тип.  
  
- Корневой элемент должен сопоставляться с универсальным типом по крайней мере с одним аргументом типа. Например, <xref:System.Windows.Navigation.PageFunction%601>. Страничные функции являются основным сценарием для поддержки общего использования XAML в WPF.  
  
- Элемент объекта XAML корневого элемента для универсального класса должен также объявлять разделяемый класс `x:Class`с помощью. Это справедливо даже при определении действия построения WPF.  
  
- `x:TypeArguments`невозможно сослаться на вложенные универсальные ограничения.  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a>XAML 2009 или XAML 2006 без зависимостей WPF 3,0 или WPF 3,5  
 В .NET Framework службах XAML для XAML 2006 или XAML 2009 ограничения, связанные с WPF, для универсального использования XAML нестрогие. Можно создать экземпляр универсального элемента объекта в любой позиции в разметке XAML, которую может поддерживать система резервных типов и модель объектов.  
  
 При использовании XAML 2009 вместо сопоставления базовых типов CLR для получения типов XAML для общих языковых примитивов можно использовать [встроенные типы для общих примитивов языка XAML](built-in-types-for-common-xaml-language-primitives.md) в качестве информационных элементов в `typeString`. Например, можно объявить следующее (сопоставление префиксов не показано, но x является пространством имен XAML языка XAML для XAML 2009):  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 В WPF и при нацеливании на .NET Framework 4 можно использовать функции XAML 2009 вместе с `x:TypeArguments` , но только для свободного XAML (XAML, не компилируемого разметкой). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009. Если необходимо скомпилировать XAML в разметку, необходимо использовать ограничения, указанные в разделе "использование XAML 2006 и универсального кода XAML WPF".  
  
## <a name="see-also"></a>См. также

- [Директива x:Class](x-class-directive.md)
- [Расширение разметки x:Type](x-type-markup-extension.md)
- [Встроенные типы для общих примитивов языка XAML](built-in-types-for-common-xaml-language-primitives.md)
- [Универсальные шаблоны в XAML](generics-in-xaml.md)
