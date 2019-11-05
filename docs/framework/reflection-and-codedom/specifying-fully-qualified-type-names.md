---
title: Указание полных имен типов
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: 707c71482196d789ed9a88db34af048ec57734fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130035"
---
# <a name="specifying-fully-qualified-type-names"></a>Определение полных имен типов

Для выполнения различных операций отражения необходимо задавать имена типов. Полное имя типа состоит из спецификации имени сборки, спецификации пространства имен и имени типа. Спецификации имен типов используются такими методами, как <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> и <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.

## <a name="grammar-for-type-names"></a>Грамматика для имен типов

 Эта грамматика определяет синтаксис формальных языков. Приведенная ниже таблица содержит список лексических правил, описывающих порядок распознавания допустимых входных данных. Терминальные слова (элементы, дальнейшее сокращение которых невозможно) отображаются прописными буквами. Нетерминальные слова (допускающие сокращение) содержат прописные буквы вместе со строчными или заключены в одинарные кавычки, причем одинарные кавычки (') не являются частью синтаксиса. Символ вертикальной черты (&#124;) обозначает правила, у которых есть подправила.

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a>Определение специальных символов

В имени типа IDENTIFIER — любое допустимое имя, определяемое правилами языка.

Приведенные ниже лексемы при использовании в составе IDENTIFIER отделяются escape-символом в виде обратной косой черты (\\).

|Токен|Смысл|
|-----------|-------------|
|\\,|Разделитель сборок.|
|\\+|Разделитель вложенных типов.|
|\\&|Ссылочный тип.|
|\\*|Тип указателя.|
|\\[|Ограничитель размерности массива.|
|\\]|Ограничитель размерности массива.|
|\\|Обратная косая черта ставится перед точкой только в том случае, если точка включена в спецификацию массива. Для точек в спецификации NamespaceSpec обратная косая черта не требуется.|
|\\\|Обратная косая черта, если она используется в качестве строкового литерала.|

Следует заметить, что для всех компонентов спецификации TypeSpec, кроме AssemblyNameSpec, пробелы существенны. В AssemblyNameSpec пробелы перед разделителем "," существенны, а пробелы после "," игнорируются.

Классы отражения, такие как <xref:System.Type.FullName%2A?displayProperty=nameWithType>, возвращают искаженное имя, которое можно использовать при вызове метода <xref:System.Type.GetType%2A>, например `MyType.GetType(myType.FullName)`.

Например, полное имя типа может иметь следующий вид: `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.

Если бы использовалось пространство имен `Ozzy.Out+Back`, перед плюсом должна была бы стоять обратная косая черта. В противном случае синтаксический анализатор интерпретировал бы плюс как разделитель вложений. Отражение порождает эту строку в следующем виде: `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.

## <a name="specifying-assembly-names"></a>Определение имен сборок

Единственным обязательным компонентом спецификации имени сборки является текстовое имя сборки (IDENTIFIER). За ним может следовать список разделенных запятыми пар "свойство/значение", как показано в таблице ниже. Имя IDENTIFIER должно удовлетворять правилам именования файлов. Регистр символов в имени IDENTIFIER не учитывается.

|Имя свойства.|Описание|Допустимые значения|
|-------------------|-----------------|----------------------|
|**Version**|Номер версии сборки|*Major.Minor.Build.Revision*, где *Major*, *Minor*, *Build* и *Revision* являются целочисленными значениями в диапазоне от 0 до 65 535 включительно.|
|**PublicKey**|Полный открытый ключ|Строковое значение полного открытого ключа в шестнадцатеричном формате. Чтобы явным образом описать сборку как закрытую, необходимо задать пустую ссылку (**Nothing** в Visual Basic).|
|**PublicKeyToken**|Токен открытого ключа (8-байтовый хэш-код полного открытого ключа)|Строковое значение токена открытого ключа в шестнадцатеричном формате. Чтобы явным образом описать сборку как закрытую, необходимо задать пустую ссылку (**Nothing** в Visual Basic).|
|**Язык и региональные параметры**|Язык и региональные параметры сборки|Язык и региональные параметры сборки в формате RFC-1766 или нейтральная среда для сборок, независимых от языков (не сопутствующих).|
|**Пользовательский**|Пользовательский BLOB-объект. В настоящее время используется только в сборках, созданных [генератором образов в машинном коде (Ngen)](../tools/ngen-exe-native-image-generator.md).|Настраиваемая строка, с помощью которой генератор образов в машинном коде уведомляет кэш сборок о том, что устанавливаемая сборка является образом в машинном коде и должна быть установлена в кэш образов в машинном коде. Также называется zap-строкой.|

В приведенном ниже примере демонстрируется спецификация **AssemblyName** для сборки с простым именем, а также заданными по умолчанию языком и региональными параметрами.

```csharp
com.microsoft.crypto, Culture=""
```

В приведенном ниже примере показана полностью определенная ссылка на сборку со строгим именем, для которой установлены язык и региональные параметры —"en".

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

В каждом из приведенных ниже примеров приводится частично определенное имя **AssemblyName**, которое подходит для сборки как с простым, так и со строгим именем.

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

В каждом из приведенных ниже примеров приводится частично определенное имя **AssemblyName**, которое подходит только для сборки с простым именем.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

В каждом из приведенных ниже примеров приводится частично определенное имя **AssemblyName**, которое подходит только для сборки со строгим именем.

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a>Определение универсальных типов

SimpleTypeSpec\`NUMBER представляет открытый универсальный тип с параметрами универсального типа от 1 до *n*. Например, чтобы получить ссылку на List\<T> для открытого универсального типа или List\<String> для закрытого универсального типа, используйте ``Type.GetType("System.Collections.Generic.List`1")``. Чтобы получить ссылку на Dictionary\<TKey,TValue> для универсального типа, используйте ``Type.GetType("System.Collections.Generic.Dictionary`2")``.

## <a name="specifying-pointers"></a>Определение указателей

Спецификация SimpleTypeSpec* представляет неуправляемый указатель. Например, для получения указателя на тип MyType можно использовать вызов метода `Type.GetType("MyType*")`. Для получения указателя на указатель на тип MyType используется вызов `Type.GetType("MyType**")`.

## <a name="specifying-references"></a>Определение ссылок

Спецификация SimpleTypeSpec & представляет управляемый указатель или ссылку. Например, для получения ссылки на тип MyType можно использовать вызов `Type.GetType("MyType &")`. Обратите внимание, что ссылки, в отличие от указателей, ограничены одним уровнем.

## <a name="specifying-arrays"></a>Определение массивов

В БНФ спецификация ReflectionEmitDimension применяется только в отношении неполных определений типов, полученных с использованием метода <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>. К неполным определениям типов относятся объекты <xref:System.Reflection.Emit.TypeBuilder>, созданные с помощью метода <xref:System.Reflection.Emit?displayProperty=nameWithType>, но для которых не был выполнен вызов <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>. Спецификацию ReflectionDimension можно использовать для получения любого полного определения типа, то есть типа, который уже загружен.

Доступ к массиву при отражении осуществляется путем указания размерности массива:

- `Type.GetType("MyArray[]")` — получение одномерного массива с нижней границей 0.

- `Type.GetType("MyArray[*]")` — получение одномерного массива с неизвестной нижней границей.
- `Type.GetType("MyArray[][]")` — получение массива двумерных массивов.

- `Type.GetType("MyArray[*,*]")` и `Type.GetType("MyArray[,]")` — получение прямоугольного двумерного массива с неизвестными нижними границами.

Обратите внимание, что с точки зрения среды выполнения `MyArray[] != MyArray[*]`, но для многомерных массивов эти обозначения эквивалентны. Другими словами, выражение `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` дает значение **true**.

Для метода **ModuleBuilder.GetType** `MyArray[0..5]` указывает одномерный массив размером 6 с нижней границей 0. `MyArray[4…]` указывает одномерный массив неизвестного размера с нижней границей 4.

## <a name="see-also"></a>См. также

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [Просмотр сведений о типах](viewing-type-information.md)
