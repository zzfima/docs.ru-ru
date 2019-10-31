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
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a><span data-ttu-id="1b770-102">Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения</span><span class="sxs-lookup"><span data-stu-id="1b770-102">How to: Load Assemblies into the Reflection-Only Context</span></span>

<span data-ttu-id="1b770-103">Контекст загрузки, предназначенный только для отражения, позволяет просматривать сборки, скомпилированные для других платформ или для других версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1b770-103">The reflection-only load context allows you to examine assemblies compiled for other platforms or for other versions of the .NET Framework.</span></span> <span data-ttu-id="1b770-104">Код, загруженный в этот контекст, может быть просмотрен, но не может быть выполнен.</span><span class="sxs-lookup"><span data-stu-id="1b770-104">Code loaded into this context can only be examined; it cannot be executed.</span></span> <span data-ttu-id="1b770-105">Это означает, что объекты не могут быть созданы, так как невозможно будет запустить конструкторы.</span><span class="sxs-lookup"><span data-stu-id="1b770-105">This means that objects cannot be created, because constructors cannot be executed.</span></span> <span data-ttu-id="1b770-106">Так как код не может быть выполнен, зависимости не будут загружены автоматически.</span><span class="sxs-lookup"><span data-stu-id="1b770-106">Because the code cannot be executed, dependencies are not automatically loaded.</span></span> <span data-ttu-id="1b770-107">Если следует их просмотреть, придется загрузить их самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="1b770-107">If you need to examine them, you must load them yourself.</span></span>

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a><span data-ttu-id="1b770-108">Загрузка сборки в контекст загрузки, предназначенный только для отражения</span><span class="sxs-lookup"><span data-stu-id="1b770-108">To load an assembly into the reflection-only load context</span></span>

1. <span data-ttu-id="1b770-109">Используйте перегрузку метода <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> для загрузки сборки по ее отображаемому имени или метод <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> для загрузки сборки по ее пути.</span><span class="sxs-lookup"><span data-stu-id="1b770-109">Use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> method overload to load the assembly given its display name, or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> method to load the assembly given its path.</span></span> <span data-ttu-id="1b770-110">Если сборка является двоичным образом, используйте перегрузку метода <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="1b770-110">If the assembly is a binary image, use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> method overload.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1b770-111">Невозможно использовать контекст, предназначенный только для отражения, для загрузки версии mscorlib.dll из версии .NET Framework, отличной от версии контекста выполнения.</span><span class="sxs-lookup"><span data-stu-id="1b770-111">You cannot use the reflection-only context to load a version of mscorlib.dll from a version of the .NET Framework other than the version in the execution context.</span></span>

2. <span data-ttu-id="1b770-112">Если сборка имеет зависимости, метод <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> их не загружает.</span><span class="sxs-lookup"><span data-stu-id="1b770-112">If the assembly has dependencies, the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> method does not load them.</span></span> <span data-ttu-id="1b770-113">Если следует их просмотреть, придется загрузить их самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="1b770-113">If you need to examine them, you must load them yourself.</span></span>

3. <span data-ttu-id="1b770-114">Определите, загружена ли сборка в контекст, предназначенный только для отражения, с помощью свойства сборки <xref:System.Reflection.Assembly.ReflectionOnly%2A>.</span><span class="sxs-lookup"><span data-stu-id="1b770-114">Determine whether an assembly is loaded into the reflection-only context by using the assembly's <xref:System.Reflection.Assembly.ReflectionOnly%2A> property.</span></span>

4. <span data-ttu-id="1b770-115">Если атрибуты были применены к сборке или к типам сборки, просмотрите эти атрибуты с помощью класса <xref:System.Reflection.CustomAttributeData>, чтобы убедиться в отсутствии попыток выполнения кода в контексте, предназначенном только для отражения.</span><span class="sxs-lookup"><span data-stu-id="1b770-115">If attributes have been applied to the assembly or to types in the assembly, examine those attributes by using the <xref:System.Reflection.CustomAttributeData> class to ensure that no attempt is made to execute code in the reflection-only context.</span></span> <span data-ttu-id="1b770-116">Используйте соответствующую перегрузку метода <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> для получения объектов <xref:System.Reflection.CustomAttributeData>, представляющих атрибуты, применимые к сборке, элементу, модулю или параметру.</span><span class="sxs-lookup"><span data-stu-id="1b770-116">Use the appropriate overload of the <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method to obtain <xref:System.Reflection.CustomAttributeData> objects representing the attributes applied to an assembly, member, module, or parameter.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1b770-117">Атрибуты, применяемые к сборке или ее содержимому, могут быть определены в сборке или в другой сборке, загруженной в контекст, предназначенный только для отражения.</span><span class="sxs-lookup"><span data-stu-id="1b770-117">Attributes applied to the assembly or to its contents might be defined in the assembly, or they might be defined in another assembly loaded into the reflection-only context.</span></span> <span data-ttu-id="1b770-118">Невозможно заведомо узнать, где определены атрибуты.</span><span class="sxs-lookup"><span data-stu-id="1b770-118">There is no way to tell in advance where the attributes are defined.</span></span>

## <a name="example"></a><span data-ttu-id="1b770-119">Пример</span><span class="sxs-lookup"><span data-stu-id="1b770-119">Example</span></span>

<span data-ttu-id="1b770-120">В следующем примере кода показано, как просмотреть атрибуты, примененные к сборке, загруженной в контекст, предназначенный только для отражения.</span><span class="sxs-lookup"><span data-stu-id="1b770-120">The following code example shows how to examine the attributes applied to an assembly loaded into the reflection-only context.</span></span>

<span data-ttu-id="1b770-121">В этом примере кода определяется пользовательский атрибут с двумя конструкторами и одним свойством.</span><span class="sxs-lookup"><span data-stu-id="1b770-121">The code example defines a custom attribute with two constructors and one property.</span></span> <span data-ttu-id="1b770-122">Данный атрибут применяется к сборке, к объявленному в ней типу, к методу типа и к параметру этого метода.</span><span class="sxs-lookup"><span data-stu-id="1b770-122">The attribute is applied to the assembly, to a type declared in the assembly, to a method of the type, and to a parameter of the method.</span></span> <span data-ttu-id="1b770-123">Во время выполнения сборка загружает себя в контекст, предназначенный только для отображения, и выводит сведения о настраиваемых атрибутах, которые были применены к ней, к ее типам, а также к содержащимся в ней элементам.</span><span class="sxs-lookup"><span data-stu-id="1b770-123">When executed, the assembly loads itself into the reflection-only context and displays information about the custom attributes that were applied to it and to the types and members it contains.</span></span>

> [!NOTE]
> <span data-ttu-id="1b770-124">Чтобы упростить этот пример кода, сборка сама себя загружает и просматривает.</span><span class="sxs-lookup"><span data-stu-id="1b770-124">To simplify the code example, the assembly loads and examines itself.</span></span> <span data-ttu-id="1b770-125">Как правило, одна сборка не загружается одновременно в контекст выполнения и в контекст, предназначенный только для отражения.</span><span class="sxs-lookup"><span data-stu-id="1b770-125">Normally, you would not expect to find the same assembly loaded into both the execution context and the reflection-only context.</span></span>

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="1b770-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1b770-126">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
