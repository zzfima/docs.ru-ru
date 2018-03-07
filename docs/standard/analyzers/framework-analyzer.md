---
title: "Анализаторы безопасности .NET — .NET"
description: "Сведения об использовании анализаторов безопасности .NET в пакете анализаторов .NET Framework для поиска и устранения угроз безопасности"
keywords: .NET, .NET Core
author: billwagner
ms.author: billwagner
ms.date: 01/25/2018
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.openlocfilehash: 06a387d72d06609182c8894dd874b241a5d7b69c
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2018
---
# <a name="the-net-framework-analyzer"></a><span data-ttu-id="21138-104">Анализатор .NET Framework</span><span class="sxs-lookup"><span data-stu-id="21138-104">The .NET Framework Analyzer</span></span>

<span data-ttu-id="21138-105">Анализатор .NET Framework можно использовать для поиска потенциальных проблем в коде приложения на основе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21138-105">You can use the .NET Framework Analyzer to find potential issues in your .NET Framework-based application code.</span></span> <span data-ttu-id="21138-106">Этот анализатор находит потенциальные проблемы и предлагает решения по их устранению.</span><span class="sxs-lookup"><span data-stu-id="21138-106">This analyzer finds potential issues and suggests fixes to them.</span></span>

<span data-ttu-id="21138-107">Анализатор запускается в интерактивном режиме в Visual Studio при написании кода или в составе сборки CI.</span><span class="sxs-lookup"><span data-stu-id="21138-107">The analyzer runs interactively in Visual Studio as you write your code or as part of a CI build.</span></span> <span data-ttu-id="21138-108">В процессе разработки анализатор необходимо добавить в проект как можно раньше.</span><span class="sxs-lookup"><span data-stu-id="21138-108">You should add the analyzer to your project as early as possible in your development.</span></span> <span data-ttu-id="21138-109">Чем раньше вы обнаружите какие-либо потенциальные проблемы в коде, тем легче вы их исправите.</span><span class="sxs-lookup"><span data-stu-id="21138-109">The sooner you find any potential issues in your code, the easier they are to fix.</span></span> <span data-ttu-id="21138-110">Однако анализатор можно добавить в любое время на этапе разработки.</span><span class="sxs-lookup"><span data-stu-id="21138-110">However, you can add it at any time in the development cycle.</span></span> <span data-ttu-id="21138-111">Он выявляет проблемы с существующим кодом и предупреждает о новых проблемах в ходе разработки.</span><span class="sxs-lookup"><span data-stu-id="21138-111">It finds any issues with the existing code and warns about new issues as you keep developing.</span></span>

## <a name="installing-and-configuring-the-net-framework-analyzer"></a><span data-ttu-id="21138-112">Установка и настройка анализатора .NET Framework</span><span class="sxs-lookup"><span data-stu-id="21138-112">Installing and configuring the .NET Framework Analyzer</span></span>

<span data-ttu-id="21138-113">Анализаторы безопасности .NET устанавливаются в виде пакета NuGet в каждом проекте, где они будут запускаться.</span><span class="sxs-lookup"><span data-stu-id="21138-113">The .NET Security Analyzers must be installed as a NuGet package on every project where you want them to run.</span></span> <span data-ttu-id="21138-114">Добавлять их в проект должен один разработчик.</span><span class="sxs-lookup"><span data-stu-id="21138-114">Only one developer needs to add them to the project.</span></span> <span data-ttu-id="21138-115">Пакет анализатора является зависимостью проекта и будет выполняться на каждом компьютере разработчика с обновленным решением.</span><span class="sxs-lookup"><span data-stu-id="21138-115">The analyzer package is a project dependency and will run on every developer's machine once it has the updated solution.</span></span>

<span data-ttu-id="21138-116">Анализатор .NET Framework входит в пакет NuGet [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/).</span><span class="sxs-lookup"><span data-stu-id="21138-116">The .NET Framework Analyzer is delivered in the [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet package.</span></span> <span data-ttu-id="21138-117">Этот пакет содержит только анализаторы, соответствующие .NET Framework, в число которых входят анализаторы безопасности.</span><span class="sxs-lookup"><span data-stu-id="21138-117">This package provides only the analyzers specific to the .NET Framework, which includes security analyzers.</span></span> <span data-ttu-id="21138-118">В большинстве случаев требуется пакет NuGet [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers).</span><span class="sxs-lookup"><span data-stu-id="21138-118">In most cases, you'll want the [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet package.</span></span> <span data-ttu-id="21138-119">Пакет FxCopAnalyzers содержит все анализаторы платформы, включенные в пакет Framework.Analyzers, а также следующие анализаторы:</span><span class="sxs-lookup"><span data-stu-id="21138-119">The FxCopAnalyzers aggregate package contains all the framework analyzers included in the Framework.Analyzers package as well as the following analyzers:</span></span>
- <span data-ttu-id="21138-120">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): предоставляет общие рекомендации и инструкции по стандартным API-интерфейсам .NET Standard;</span><span class="sxs-lookup"><span data-stu-id="21138-120">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Provides general guidance and guidance for .NET Standard APIs</span></span>
- <span data-ttu-id="21138-121">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): предоставляет анализаторы, соответствующие API-интерфейсам .NET Core;</span><span class="sxs-lookup"><span data-stu-id="21138-121">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Provides analyzers specific to .NET Core APIs.</span></span>
- <span data-ttu-id="21138-122">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): предоставляет рекомендации по тексту, включаемому в виде кода, а также комментарии.</span><span class="sxs-lookup"><span data-stu-id="21138-122">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Provides guidance for text included as code, including comments.</span></span>

<span data-ttu-id="21138-123">Чтобы установить его, щелкните правой кнопкой мыши проект и выберите пункт "Управление зависимостями".</span><span class="sxs-lookup"><span data-stu-id="21138-123">To install it, right-click on the project, and select "Manage Dependencies".</span></span>
<span data-ttu-id="21138-124">В обозревателе NuGet найдите "Анализатор NetFramework" или "Анализатор Fx Cop".</span><span class="sxs-lookup"><span data-stu-id="21138-124">From the NuGet explorer, search for "NetFramework Analyzer", or if you prefer, "Fx Cop Analyzer".</span></span> <span data-ttu-id="21138-125">Установите последнюю стабильную версию во всех проектах в решении.</span><span class="sxs-lookup"><span data-stu-id="21138-125">Install the latest stable version in all projects in your solution.</span></span>

## <a name="using-the-net-framework-analyzer"></a><span data-ttu-id="21138-126">Использование анализатора .NET Framework</span><span class="sxs-lookup"><span data-stu-id="21138-126">Using the .NET Framework Analyzer</span></span>

<span data-ttu-id="21138-127">После установки пакета NuGet выполните сборку решения.</span><span class="sxs-lookup"><span data-stu-id="21138-127">Once the NuGet package is installed, build your solution.</span></span> <span data-ttu-id="21138-128">Анализатор сообщит о любых проблемах, которые будут найдены в базе кода.</span><span class="sxs-lookup"><span data-stu-id="21138-128">The analyzer will report any issues it locates in your codebase.</span></span> <span data-ttu-id="21138-129">Проблемы выводятся как предупреждения в окне списка ошибок в Visual Studio, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="21138-129">The issues are reported as warnings in the Visual Studio Error List window, as shown in the following image:</span></span>

![Проблемы, о которых сообщает анализатор Framework](./media/framework-analyzers-2.png)

<span data-ttu-id="21138-131">При написании кода потенциальные проблемы выделяются волнистыми линиями.</span><span class="sxs-lookup"><span data-stu-id="21138-131">As you write code, you see squiggles underneath any potential issue in your code.</span></span>
<span data-ttu-id="21138-132">Наведите указатель мыши на любую проблему и просмотрите сведения о ней, а также предложения по возможному исправлению, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="21138-132">Hover over any issue and you see details about the issue, and suggestions for any possible fix, as shown in the following image:</span></span>

![интерактивный отчет о проблемах, обнаруженных анализатором платформы](./media/framework-analyzers-1.png)

<span data-ttu-id="21138-134">Анализатор изучает код в решении и отображает список предупреждений по каждой найденной проблеме.</span><span class="sxs-lookup"><span data-stu-id="21138-134">The analyzers examine the code in your solution and provide you with a list of warnings for any of these issues:</span></span>

### <a name="ca1058-types-should-not-extend-certain-base-types"></a><span data-ttu-id="21138-135">CA1058: типы не должны расширять определенные базовые типы</span><span class="sxs-lookup"><span data-stu-id="21138-135">CA1058: Types should not extend certain base types</span></span>

<span data-ttu-id="21138-136">В .NET Framework существует незначительное количество типов, от которых не следует выполнять прямое наследование.</span><span class="sxs-lookup"><span data-stu-id="21138-136">There are a small number of types in the .NET Framework that you should not derived from directly.</span></span> 

<span data-ttu-id="21138-137">**Категория:** разработка</span><span class="sxs-lookup"><span data-stu-id="21138-137">**Category:** Design</span></span>

<span data-ttu-id="21138-138">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-138">**Severity:** Warning</span></span>

<span data-ttu-id="21138-139">Дополнительные сведения: [CA1058: типы не должны расширять определенные базовые типы](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span><span class="sxs-lookup"><span data-stu-id="21138-139">Additional information: [CA:1058: Types should not extend certain base types](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span></span>

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a><span data-ttu-id="21138-140">CA2153: не перехватывайте исключения поврежденного состояния</span><span class="sxs-lookup"><span data-stu-id="21138-140">CA2153: Do not catch corrupted state exceptions</span></span>

<span data-ttu-id="21138-141">Перехват исключений поврежденного состояния может маскировать ошибки (например, нарушение прав доступа), что приведет к несогласованному состоянию выполнения или упростит возможность нарушения безопасности системы злоумышленниками.</span><span class="sxs-lookup"><span data-stu-id="21138-141">Catching corrupted state exceptions could mask errors (such as access violations), resulting in an inconsistent state of execution or making it easier for attackers to compromise a system.</span></span> <span data-ttu-id="21138-142">Вместо этого следует перехватывать и обрабатывать более конкретный набор типов исключений или заново создать исключение.</span><span class="sxs-lookup"><span data-stu-id="21138-142">Instead, catch and handle a more specific set of exception type(s) or re-throw the exception</span></span>

<span data-ttu-id="21138-143">**Категория:** безопасность</span><span class="sxs-lookup"><span data-stu-id="21138-143">**Category:** Security</span></span>

<span data-ttu-id="21138-144">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-144">**Severity:** Warning</span></span>

<span data-ttu-id="21138-145">Дополнительные сведения: [## CA2153: не перехватывайте исключения поврежденного состояния](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span><span class="sxs-lookup"><span data-stu-id="21138-145">Additional information: [## CA2153: Do not catch corrupted state exceptions](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span></span>

### <a name="ca2229-implement-serialization-constructors"></a><span data-ttu-id="21138-146">CA2229: применяйте конструкторы сериализации</span><span class="sxs-lookup"><span data-stu-id="21138-146">CA2229: Implement serialization constructors</span></span>

<span data-ttu-id="21138-147">Анализатор генерирует это предупреждение, когда вы создаете тип, реализующий интерфейс <xref:System.Runtime.Serialization.ISerializable>, но не определяющий необходимый конструктор сериализации.</span><span class="sxs-lookup"><span data-stu-id="21138-147">The analyzer generates this warning when you create a type that implements the <xref:System.Runtime.Serialization.ISerializable> interface but does not define the required serialization constructor.</span></span> <span data-ttu-id="21138-148">Чтобы устранить нарушение этого правила, реализуйте конструктор сериализации.</span><span class="sxs-lookup"><span data-stu-id="21138-148">To fix a violation of this rule, implement the serialization constructor.</span></span> <span data-ttu-id="21138-149">Для запечатанного класса конструктор должен быть закрытым, а в иных случаях — защищенным.</span><span class="sxs-lookup"><span data-stu-id="21138-149">For a sealed class, make the constructor private; otherwise, make it protected.</span></span> <span data-ttu-id="21138-150">Конструктор сериализации имеет следующую сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="21138-150">The serialization constructor has the following signature:</span></span>

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

<span data-ttu-id="21138-151">**Категория:** использование</span><span class="sxs-lookup"><span data-stu-id="21138-151">**Category:** Usage</span></span>

<span data-ttu-id="21138-152">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-152">**Severity:** Warning</span></span>

<span data-ttu-id="21138-153">Дополнительные сведения: [CA2229: применяйте конструкторы сериализации](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span><span class="sxs-lookup"><span data-stu-id="21138-153">Additional information: [CA2229: Implement serialization constructors](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span></span>

### <a name="ca2235-mark-all-non-serializable-fields"></a><span data-ttu-id="21138-154">CA2235: помечайте все несериализуемые поля</span><span class="sxs-lookup"><span data-stu-id="21138-154">CA2235: Mark all non-serializable fields</span></span>

<span data-ttu-id="21138-155">Экземпляр поля несериализуемого типа объявлен в сериализуемом типе.</span><span class="sxs-lookup"><span data-stu-id="21138-155">An instance field of a type that is not serializable is declared in a type that is serializable.</span></span> <span data-ttu-id="21138-156">Необходимо явно пометить это поле с <xref:System.NonSerializedAttribute>, чтобы устранить это предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-156">You must explicitly mark that field with the <xref:System.NonSerializedAttribute> to fix this warning.</span></span>

<span data-ttu-id="21138-157">**Категория:** использование</span><span class="sxs-lookup"><span data-stu-id="21138-157">**Category:** Usage</span></span>

<span data-ttu-id="21138-158">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-158">**Severity:** Warning</span></span>

<span data-ttu-id="21138-159">Дополнительные сведения: [CA2235: помечайте все несериализуемые поля](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span><span class="sxs-lookup"><span data-stu-id="21138-159">Additional information: [CA2235: Mark all non-serializable fields](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span></span>

### <a name="ca2237-mark-iserializable-types-with-serializable"></a><span data-ttu-id="21138-160">CA2237: пометьте типы ISerializable атрибутом serializable</span><span class="sxs-lookup"><span data-stu-id="21138-160">CA2237: Mark ISerializable types with serializable</span></span>

<span data-ttu-id="21138-161">Чтобы среда CLR распознавала тип как сериализуемый, он должен быть помечен атрибутом <xref:System.SerializableAttribute>, даже если тип использует пользовательскую процедуру сериализации посредством реализации интерфейса <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="21138-161">To be recognized by the common language runtime as serializable, types must be marked by using the <xref:System.SerializableAttribute> attribute even when the type uses a custom serialization routine by implementing the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

<span data-ttu-id="21138-162">**Категория:** использование</span><span class="sxs-lookup"><span data-stu-id="21138-162">**Category:** Usage</span></span>

<span data-ttu-id="21138-163">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-163">**Severity:** Warning</span></span>

<span data-ttu-id="21138-164">Дополнительные сведения: [CA2237: пометьте типы ISerializable атрибутом serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="21138-164">Additional information: [CA2237: Mark ISerializable types with serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca3075-insecure-dtd-processing-in-xml"></a><span data-ttu-id="21138-165">CA3075: обработка небезопасных DTD в XML</span><span class="sxs-lookup"><span data-stu-id="21138-165">CA3075: Insecure DTD processing in XML</span></span>

<span data-ttu-id="21138-166">Если вы используете небезопасные экземпляры <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> или ссылаетесь на источники внешних сущностей, средство синтаксического анализа может принять недоверенные входные данные и раскрыть конфиденциальную информацию злоумышленникам.</span><span class="sxs-lookup"><span data-stu-id="21138-166">If you use insecure <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instances or reference external entity sources, the parser may accept untrusted input and disclose sensitive information to attackers.</span></span>  

<span data-ttu-id="21138-167">**Категория:** безопасность</span><span class="sxs-lookup"><span data-stu-id="21138-167">**Category:** Security</span></span>

<span data-ttu-id="21138-168">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-168">**Severity:** Warning</span></span>

<span data-ttu-id="21138-169">Дополнительные сведения: [A3075: обработка небезопасных DTD в XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="21138-169">Additional information: [A3075: Insecure DTD processing in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>


### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a><span data-ttu-id="21138-170">CA5350: не используйте ненадежные алгоритмы шифрования</span><span class="sxs-lookup"><span data-stu-id="21138-170">CA5350: Do not use weak cryptographic algorithms</span></span>

<span data-ttu-id="21138-171">С течением времени надежность алгоритмов шифрования снижается, так как атаки становятся более сложными.</span><span class="sxs-lookup"><span data-stu-id="21138-171">Cryptographic algorithms degrade over time as attacks become more advanced.</span></span> <span data-ttu-id="21138-172">В зависимости от типа и применения этого алгоритма шифрования дальнейшее снижение его криптографической стойкости может привести к тому, что злоумышленники смогут читать зашифрованные сообщения, искажать зашифрованные сообщения, подделывать цифровые подписи, незаконно использовать хэшированное содержимое или иным образом нарушать безопасность криптосистемы, основанной на данном алгоритме.</span><span class="sxs-lookup"><span data-stu-id="21138-172">Depending on the type and application of this cryptographic algorithm, further degradation of its cryptographic strength may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="21138-173">В целях шифрования используйте алгоритм AES (AES-256, AES 192 и AES-128) с длиной ключа не меньше 128 бит.</span><span class="sxs-lookup"><span data-stu-id="21138-173">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="21138-174">В целях хэширования используйте функцию хэширования семейства SHA-2, например SHA-2 512, SHA-2 384 или SHA-2 256.</span><span class="sxs-lookup"><span data-stu-id="21138-174">For hashing, use a hashing function in the SHA-2 family, such as SHA-2 512, SHA-2 384, or SHA-2 256.</span></span>

<span data-ttu-id="21138-175">**Категория:** безопасность</span><span class="sxs-lookup"><span data-stu-id="21138-175">**Category:** Security</span></span>

<span data-ttu-id="21138-176">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-176">**Severity:** Warning</span></span>

<span data-ttu-id="21138-177">Дополнительные сведения: [CA5350: не используйте ненадежные алгоритмы шифрования](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="21138-177">Additional information: [CA5350: Do not use weak cryptographic algorithms](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span></span>

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a><span data-ttu-id="21138-178">CA5351: не используйте ослабленные алгоритмы шифрования</span><span class="sxs-lookup"><span data-stu-id="21138-178">CA5351: Do not use broken cryptographic algorithms</span></span>

<span data-ttu-id="21138-179">Существует атака, допускающая нарушение этого алгоритма вычислительно выполнимым способом.</span><span class="sxs-lookup"><span data-stu-id="21138-179">An attack making it computationally feasible to break this algorithm exists.</span></span> <span data-ttu-id="21138-180">С ее помощью злоумышленники могут разрушить возможности шифрования этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="21138-180">This allows attackers to break the cryptographic guarantees it is designed to provide.</span></span> <span data-ttu-id="21138-181">В этом случае в зависимости от типа и применения этого алгоритма шифрования злоумышленники смогут читать зашифрованные сообщения, искажать зашифрованные сообщения, подделывать цифровые подписи, незаконно использовать хэшированное содержимое или иным образом нарушать безопасность криптосистемы, основанной на данном алгоритме.</span><span class="sxs-lookup"><span data-stu-id="21138-181">Depending on the type and application of this cryptographic algorithm, this may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="21138-182">В целях шифрования используйте алгоритм AES (AES-256, AES 192 и AES-128) с длиной ключа не меньше 128 бит.</span><span class="sxs-lookup"><span data-stu-id="21138-182">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="21138-183">В целях хэширования используйте функцию хэширования семейства SHA-2, например SHA512, SHA384 или SHA256.</span><span class="sxs-lookup"><span data-stu-id="21138-183">For hashing, use a hashing function in the SHA-2 family, such as SHA512, SHA384, or SHA256.</span></span> <span data-ttu-id="21138-184">Для цифровых подписей используйте RSA с длиной ключа не меньше 2048 бит или ECDSA с длиной ключа не меньше 256 бит.</span><span class="sxs-lookup"><span data-stu-id="21138-184">For digital signatures, use RSA with a key length greater than or equal to 2048-bits, or ECDSA with a key length greater than or equal to 256 bits.</span></span>

<span data-ttu-id="21138-185">**Категория:** безопасность</span><span class="sxs-lookup"><span data-stu-id="21138-185">**Category:** Security</span></span>

<span data-ttu-id="21138-186">**Серьезность** : предупреждение.</span><span class="sxs-lookup"><span data-stu-id="21138-186">**Severity:** Warning</span></span>

<span data-ttu-id="21138-187">Дополнительные сведения: [CA5351: не используйте ослабленные алгоритмы шифрования](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="21138-187">Additional Information: [CA5351: Do not use broken cryptographic algorithms](/visualstudio/code-quality/ca5351-do-not-use-broken-cryptographic-algorithms)</span></span>


