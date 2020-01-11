---
title: Двоичная сериализация
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901044"
---
# <a name="binary-serialization"></a><span data-ttu-id="caa60-102">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="caa60-102">Binary serialization</span></span>

<span data-ttu-id="caa60-103">Сериализацию можно представить как процесс сохранения состояния объекта в среду хранения.</span><span class="sxs-lookup"><span data-stu-id="caa60-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="caa60-104">Во время этого процесса открытые и закрытые поля объекта и имя класса, включая сборку с классом, преобразуются в поток байтов, который затем записывается в поток данных.</span><span class="sxs-lookup"><span data-stu-id="caa60-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="caa60-105">После десериализации объекта создается точная копия исходного объекта.</span><span class="sxs-lookup"><span data-stu-id="caa60-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="caa60-106">При реализации механизма сериализации в объектно-ориентированной среде следует сделать выбор между простотой и гибкостью использования.</span><span class="sxs-lookup"><span data-stu-id="caa60-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="caa60-107">Процесс можно в значительной степени автоматизировать при условии сохранения над ним достаточного контроля.</span><span class="sxs-lookup"><span data-stu-id="caa60-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="caa60-108">Например, могут возникать ситуации, при которых недостаточно простой двоичной сериализации или по какой-либо причине необходимо определить сериализуемые поля в классе.</span><span class="sxs-lookup"><span data-stu-id="caa60-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="caa60-109">В следующих разделах исследуется надежный механизм сериализации с использованием платформы .NET и отмечается ряд важных особенностей, которые позволяют настраивать процесс в соответствии с собственными потребностями.</span><span class="sxs-lookup"><span data-stu-id="caa60-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="caa60-110">Состояние объекта, закодированного в UTF-8 или UTF-7, не сохраняется, если этот объект сериализуется и десериализуется с использованием различных версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="caa60-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="caa60-111">Двоичная сериализация позволяет изменять закрытые члены внутри объекта и, следовательно, изменять их состояние.</span><span class="sxs-lookup"><span data-stu-id="caa60-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="caa60-112">По этой причине рекомендуется использовать другие платформы сериализации, например <xref:System.Text.Json?displayProperty=fullName>, которые работают на поверхности общедоступного API.</span><span class="sxs-lookup"><span data-stu-id="caa60-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="caa60-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="caa60-113">.NET Core</span></span>

<span data-ttu-id="caa60-114">.NET Core поддерживает двоичную сериализацию для подмножества типов.</span><span class="sxs-lookup"><span data-stu-id="caa60-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="caa60-115">Список поддерживаемых типов см. в разделе [сериализуемые типы](#serializable-types) , как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="caa60-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="caa60-116">Гарантируется, что перечисленные типы будут сериализуемыми между .NET Framework 4.5.1 и более поздними версиями, а также между .NET Core 2,0 и более поздними версиями.</span><span class="sxs-lookup"><span data-stu-id="caa60-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="caa60-117">Другие реализации .NET, такие как Mono, официально не поддерживаются, но также должны работать.</span><span class="sxs-lookup"><span data-stu-id="caa60-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="caa60-118">Сериализуемые типы</span><span class="sxs-lookup"><span data-stu-id="caa60-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="caa60-119">Тип</span><span class="sxs-lookup"><span data-stu-id="caa60-119">Type</span></span> | <span data-ttu-id="caa60-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="caa60-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="caa60-121">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="caa60-122">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-123">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="caa60-124">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-125">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-126">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="caa60-127">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="caa60-128">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="caa60-129">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="caa60-130">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="caa60-131">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="caa60-132">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="caa60-133">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-134">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="caa60-135">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-136">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="caa60-137">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="caa60-138">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="caa60-139">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="caa60-140">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="caa60-141">Сериализация из .NET Framework в .NET Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="caa60-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="caa60-142">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="caa60-143">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="caa60-144">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-145">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="caa60-146">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="caa60-147">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-148">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="caa60-149">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="caa60-150">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="caa60-151">Начиная с .NET Core 2.0.2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="caa60-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="caa60-152">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="caa60-153">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="caa60-154">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="caa60-155">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="caa60-156">Если для `RemotingFormat` задано значение `SerializationFormat.Binary`, его можно использовать только в .NET Core 2,1 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="caa60-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="caa60-157">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="caa60-158">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="caa60-159">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="caa60-160">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="caa60-161">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="caa60-162">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="caa60-163">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-164">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="caa60-165">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-166">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="caa60-167">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="caa60-168">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="caa60-169">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="caa60-170">Сериализация из .NET Framework в .NET Core не поддерживается</span><span class="sxs-lookup"><span data-stu-id="caa60-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="caa60-171">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="caa60-172">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="caa60-173">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="caa60-174">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="caa60-175">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="caa60-176">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="caa60-177">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-178">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-179">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="caa60-180">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="caa60-181">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-182">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="caa60-183">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="caa60-184">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="caa60-185">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="caa60-186">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="caa60-187">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-188">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="caa60-189">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="caa60-190">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-191">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-192">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="caa60-193">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="caa60-194">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-195">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="caa60-196">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="caa60-197">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="caa60-198">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-199">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="caa60-200">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-201">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="caa60-202">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-203">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="caa60-204">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-205">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="caa60-206">Начиная с .NET Core 2.0.6.</span><span class="sxs-lookup"><span data-stu-id="caa60-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="caa60-207">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="caa60-208">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="caa60-209">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-210">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="caa60-211">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-212">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="caa60-213">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="caa60-214">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="caa60-215">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-216">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="caa60-217">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="caa60-218">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="caa60-219">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="caa60-220">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="caa60-221">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="caa60-222">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="caa60-223">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="caa60-224">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="caa60-225">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-226">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="caa60-227">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="caa60-228">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="caa60-229">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="caa60-230">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="caa60-231">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="caa60-232">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="caa60-233">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-234">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="caa60-235">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="caa60-236">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="caa60-237">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="caa60-238">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="caa60-239">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-240">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="caa60-241">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-242">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="caa60-243">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="caa60-244">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="caa60-245">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="caa60-246">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-247">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-248">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="caa60-249">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-250">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="caa60-251">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="caa60-252">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="caa60-253">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-254">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="caa60-255">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="caa60-256">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="caa60-257">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="caa60-258">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="caa60-259">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="caa60-260">Сериализация из .NET Framework в .NET Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="caa60-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="caa60-261">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-262">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="caa60-263">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="caa60-264">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="caa60-265">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-266">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="caa60-267">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="caa60-268">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="caa60-269">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="caa60-270">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="caa60-271">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="caa60-272">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="caa60-273">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="caa60-274">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="caa60-275">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-276">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="caa60-277">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-278">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="caa60-279">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="caa60-280">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-281">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="caa60-282">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="caa60-283">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="caa60-284">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-285">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="caa60-286">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="caa60-287">Ограниченные данные сериализации.</span><span class="sxs-lookup"><span data-stu-id="caa60-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-288">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="caa60-289">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="caa60-290">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="caa60-291">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="caa60-292">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="caa60-293">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="caa60-294">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="caa60-295">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="caa60-296">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="caa60-297">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="caa60-298">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="caa60-299">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="caa60-300">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="caa60-301">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="caa60-302">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="caa60-303">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-304">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="caa60-305">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="caa60-306">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-307">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="caa60-308">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="caa60-309">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-310">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="caa60-311">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="caa60-312">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-313">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="caa60-314">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="caa60-315">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-316">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="caa60-317">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="caa60-318">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="caa60-319">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="caa60-320">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="caa60-321">Не подлежит сериализации в .NET Framework 4,7 и более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="caa60-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="caa60-322">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="caa60-323">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="caa60-324">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="caa60-325">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="caa60-326">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="caa60-327">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="caa60-328">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="caa60-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="caa60-329">См. также:</span><span class="sxs-lookup"><span data-stu-id="caa60-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="caa60-330">Содержит классы, которые можно использовать для сериализации и десериализации объектов.</span><span class="sxs-lookup"><span data-stu-id="caa60-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="caa60-331">[Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="caa60-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="caa60-332">Описывает механизм XML-сериализации , входящий в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="caa60-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="caa60-333">[Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="caa60-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="caa60-334">Содержит рекомендации по написанию безопасного кода, выполняющего сериализацию.</span><span class="sxs-lookup"><span data-stu-id="caa60-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="caa60-335">\ [удаленного взаимодействия .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="caa60-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))\</span></span>
<span data-ttu-id="caa60-336">Описание различных методов, запускаемых в .NET Framework для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="caa60-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="caa60-337">[Веб-службы XML, созданные с помощью ASP.NET и клиентов веб-службы xml](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="caa60-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="caa60-338">Статьи, описывающие и объясняющие, как программировать веб-службы XML, созданные с помощью ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="caa60-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
