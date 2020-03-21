---
title: API-интерфейсы, основанные на отражении
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
ms.openlocfilehash: 1d8daceb6b744b984f86b011ad7952d0da583a79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181093"
---
# <a name="apis-that-rely-on-reflection"></a>API-интерфейсы, основанные на отражении
В некоторых случаях использование отражения в коде не очевидно, и поэтому цепочка инструментов .NET Native не сохраняет метаданные, необходимые во время выполнения. В этом разделе рассматриваются некоторые общие интерфейсы API или распространенные шаблоны программирования, которые не считаются частью API-интерфейса отражения, однако используют отражение для успешного выполнения. При их использовании в исходном коде можно добавить сведения о них в файл директив среды выполнения (. rd.xml), чтобы вызовы этих интерфейсов API не создавали исключений [MissingMetadataException](missingmetadataexception-class-net-native.md) или других исключений во время выполнения.  
  
## <a name="typemakegenerictype-method"></a>Метод Type.MakeGenericType  
 Можно динамически создать экземпляр универсального типа `AppClass<T>` путем вызова метода <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> с помощью следующего кода:  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 Для успешной работы кода во время выполнения необходимы несколько элементов метаданных. Во-первых, метаданные `Browse` для универсального типа без экземпляров, `AppClass<T>`:  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 Это позволяет вызову метода <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> завершиться успешно и вернуть допустимый объект <xref:System.Type>.  
  
 Но даже при добавлении метаданных для универсального типа без экземпляров вызов метода <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> приводит к исключению [MissingMetadataException](missingmetadataexception-class-net-native.md):  
  
Эта операция не может быть выполнена, поскольку метаданные для следующего типа были удалены по причинам производительности:  
  
`App1.AppClass`1<System.Int32>'.  
  
 Можно добавить следующую директиву времени выполнения в файл директив среды выполнения, чтобы добавить метаданные `Activate` для конкретного экземпляра, созданного над `AppClass<T>` из <xref:System.Int32?displayProperty=nameWithType>:  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"
                   Activate="Required Public" />  
```  
  
 Каждый другой экземпляр над `AppClass<T>` требует отдельной директивы, если он создается с помощью метода <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> и не используется статически.  
  
## <a name="methodinfomakegenericmethod-method"></a>Метод MethodInfo.MakeGenericMethod  
 Определенный класс `Class1` с универсальным методом `GetMethod<T>(T t)`, `GetMethod` можно вызывать с помощью отражения, используя следующий код:  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 Для успешного выполнения этого кода необходимо несколько элементов метаданных:  
  
- Метаданные `Browse` для типа, метод которого необходимо вызвать.  
  
- Метаданные `Browse` для метода, который требуется вызвать.  Если это открытый метод, добавление открытых метаданных `Browse` для содержащего типа включает и сам метод.  
  
- Динамические метаданные для вызываемого метода, чтобы делегат вызова отражения не был удален цепочкой инструментов .NET Native. В случае отсутствия динамических метаданных для метода создается следующее исключение <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType>, когда вызывается метод:  
  
    ```output
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 Следующие директивы среды выполнения гарантируют доступность всех необходимых метаданных:  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 Директива `MethodInstantiation`  обязательна для каждого отдельного экземпляра метода, который вызывается динамически, а элемент `Arguments` обновляется для отображения аргумента каждого отдельного экземпляра.  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a>Методы метода Array.CreateInstance и Type.MakeTypeArray  
 В следующем примере вызываются методы <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> и <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> на типе `Class1`.  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 При отсутствии метаданных массива возникает следующая ошибка:  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 метаданные `Browse` для типа массива требуются для динамического создания его экземпляра.  Следующая директива среды выполнения позволяет создать динамический экземпляр `Class1[]`.  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a>См. также раздел

- [Начало работы](getting-started-with-net-native.md)
- [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
