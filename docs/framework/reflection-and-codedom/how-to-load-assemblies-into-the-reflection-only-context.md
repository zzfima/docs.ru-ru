---
title: Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: cac6b3b3adf070ad6070e5c5941653f20dedd907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130101"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a>Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения

Контекст загрузки, предназначенный только для отражения, позволяет просматривать сборки, скомпилированные для других платформ или для других версий .NET Framework. Код, загруженный в этот контекст, может быть просмотрен, но не может быть выполнен. Это означает, что объекты не могут быть созданы, так как невозможно будет запустить конструкторы. Так как код не может быть выполнен, зависимости не будут загружены автоматически. Если следует их просмотреть, придется загрузить их самостоятельно.

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a>Загрузка сборки в контекст загрузки, предназначенный только для отражения

1. Используйте перегрузку метода <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> для загрузки сборки по ее отображаемому имени или метод <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> для загрузки сборки по ее пути. Если сборка является двоичным образом, используйте перегрузку метода <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>.

    > [!NOTE]
    > Невозможно использовать контекст, предназначенный только для отражения, для загрузки версии mscorlib.dll из версии .NET Framework, отличной от версии контекста выполнения.

2. Если сборка имеет зависимости, метод <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> их не загружает. Если следует их просмотреть, придется загрузить их самостоятельно.

3. Определите, загружена ли сборка в контекст, предназначенный только для отражения, с помощью свойства сборки <xref:System.Reflection.Assembly.ReflectionOnly%2A>.

4. Если атрибуты были применены к сборке или к типам сборки, просмотрите эти атрибуты с помощью класса <xref:System.Reflection.CustomAttributeData>, чтобы убедиться в отсутствии попыток выполнения кода в контексте, предназначенном только для отражения. Используйте соответствующую перегрузку метода <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> для получения объектов <xref:System.Reflection.CustomAttributeData>, представляющих атрибуты, применимые к сборке, элементу, модулю или параметру.

    > [!NOTE]
    > Атрибуты, применяемые к сборке или ее содержимому, могут быть определены в сборке или в другой сборке, загруженной в контекст, предназначенный только для отражения. Невозможно заведомо узнать, где определены атрибуты.

## <a name="example"></a>Пример

В следующем примере кода показано, как просмотреть атрибуты, примененные к сборке, загруженной в контекст, предназначенный только для отражения.

В этом примере кода определяется пользовательский атрибут с двумя конструкторами и одним свойством. Данный атрибут применяется к сборке, к объявленному в ней типу, к методу типа и к параметру этого метода. Во время выполнения сборка загружает себя в контекст, предназначенный только для отображения, и выводит сведения о настраиваемых атрибутах, которые были применены к ней, к ее типам, а также к содержащимся в ней элементам.

> [!NOTE]
> Чтобы упростить этот пример кода, сборка сама себя загружает и просматривает. Как правило, одна сборка не загружается одновременно в контекст выполнения и в контекст, предназначенный только для отражения.

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a>См. также

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
