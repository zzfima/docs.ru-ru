---
title: Прозрачный с точки зрения безопасности код, уровень 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3da3e48f898797849a5304c4884b648f47a26dd
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456571"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="7c7e0-102">Прозрачный с точки зрения безопасности код, уровень 2</span><span class="sxs-lookup"><span data-stu-id="7c7e0-102">Security-Transparent Code, Level 2</span></span>

<a name="top"></a>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="7c7e0-103">Прозрачность уровня 2 появилась в версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c7e0-103">Level 2 transparency was introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="7c7e0-104">Ключевыми элементами этой модели являются следующие компоненты: прозрачный код, надежный с точки зрения безопасности код и критический с точки зрения безопасности код.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="7c7e0-105">Прозрачный код (в том числе код с полным доверием) может вызывать только другой прозрачный или надежный с точки зрения безопасности код.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="7c7e0-106">Прозрачный код может выполнять только действия, разрешенные набором разрешений частичного доверия домена (если он существует).</span><span class="sxs-lookup"><span data-stu-id="7c7e0-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="7c7e0-107">Прозрачный код не может выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7c7e0-107">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="7c7e0-108">выполнять метод <xref:System.Security.CodeAccessPermission.Assert%2A> или повышение привилегий;</span><span class="sxs-lookup"><span data-stu-id="7c7e0-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="7c7e0-109">содержать небезопасный или непроверяемый код;</span><span class="sxs-lookup"><span data-stu-id="7c7e0-109">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="7c7e0-110">напрямую вызывать критический код;</span><span class="sxs-lookup"><span data-stu-id="7c7e0-110">Directly call critical code.</span></span>

  - <span data-ttu-id="7c7e0-111">вызывать машинный код или код с атрибутом <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>;</span><span class="sxs-lookup"><span data-stu-id="7c7e0-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="7c7e0-112">вызывать член, защищенный с помощью <xref:System.Security.Permissions.SecurityAction.LinkDemand>;</span><span class="sxs-lookup"><span data-stu-id="7c7e0-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="7c7e0-113">наследовать от критических типов.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-113">Inherit from critical types.</span></span>

  <span data-ttu-id="7c7e0-114">Кроме того, прозрачные методы не могут переопределять критические виртуальные методы или реализовывать критические методы интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="7c7e0-115">Надежный с точки зрения безопасности код имеет полное доверие, но может вызываться прозрачным кодом.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="7c7e0-116">Он предоставляет ограниченный объем кода с полным доверием. В надежном с точки зрения безопасности коде выполняются проверки на правильность и безопасность.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="7c7e0-117">Критический с точки зрения безопасности код может вызывать любой код, но не может вызываться из прозрачного кода.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

<span data-ttu-id="7c7e0-118">В этом разделе содержатся следующие подразделы.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-118">This topic contains the following sections:</span></span>

- [<span data-ttu-id="7c7e0-119">Примеры использования и поведение</span><span class="sxs-lookup"><span data-stu-id="7c7e0-119">Usage Examples and Behaviors</span></span>](#examples)

- [<span data-ttu-id="7c7e0-120">Схемы переопределения</span><span class="sxs-lookup"><span data-stu-id="7c7e0-120">Override Patterns</span></span>](#override)

- [<span data-ttu-id="7c7e0-121">Правила наследования</span><span class="sxs-lookup"><span data-stu-id="7c7e0-121">Inheritance Rules</span></span>](#inheritance)

- [<span data-ttu-id="7c7e0-122">Дополнительные сведения и правила</span><span class="sxs-lookup"><span data-stu-id="7c7e0-122">Additional Information and Rules</span></span>](#additional)

<a name="examples"></a>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="7c7e0-123">Примеры использования и поведение</span><span class="sxs-lookup"><span data-stu-id="7c7e0-123">Usage Examples and Behaviors</span></span>

<span data-ttu-id="7c7e0-124">Чтобы задать правила .NET Framework 4 (прозрачность уровня 2), используйте следующую заметку для сборки:</span><span class="sxs-lookup"><span data-stu-id="7c7e0-124">To specify .NET Framework 4 rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="7c7e0-125">Чтобы зафиксировать правила платформы .NET Framework 2.0 (прозрачность уровня 1), используйте следующую заметку:</span><span class="sxs-lookup"><span data-stu-id="7c7e0-125">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="7c7e0-126">Если сборка не содержит заметок, по умолчанию используются правила .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-126">If you do not annotate an assembly, the .NET Framework 4 rules are used by default.</span></span> <span data-ttu-id="7c7e0-127">Тем не менее, рекомендуется использовать <xref:System.Security.SecurityRulesAttribute> вместо атрибута зависимостей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-127">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="7c7e0-128">Заметка на уровне сборки</span><span class="sxs-lookup"><span data-stu-id="7c7e0-128">Assembly-wide Annotation</span></span>

<span data-ttu-id="7c7e0-129">Ниже перечислены правила, которые применяются к использованию атрибутов на уровне сборки.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-129">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="7c7e0-130">Без атрибутов: Если атрибуты не указаны, то среда выполнения рассматривает код как с точки зрения безопасности, за исключением случаев, когда с точки зрения безопасности это нарушает правило наследования (например, в том случае, при переопределении или при реализации прозрачного виртуального метода или метода интерфейса).</span><span class="sxs-lookup"><span data-stu-id="7c7e0-130">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="7c7e0-131">В таких случаях методы являются надежными с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-131">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="7c7e0-132">Если атрибут не указан, то определение правил прозрачности выполняется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-132">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="7c7e0-133">`SecurityTransparent`: Весь код является прозрачным; Вся сборка не будет ничего делать привилегированных или unsafe.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-133">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="7c7e0-134">`SecurityCritical`: Код всех типов в этой сборке является критическим, а остальной код — прозрачным.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-134">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="7c7e0-135">Этот случай аналогичен отсутствию атрибутов, но среда CLR не определяет правила прозрачности автоматически.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-135">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="7c7e0-136">Например, если переопределить виртуальный или абстрактный метод или реализовать метод интерфейса, то такой метод по умолчанию будет прозрачным.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-136">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="7c7e0-137">Следует явным образом пометить метод как `SecurityCritical` или `SecuritySafeCritical`. В противном случае при загрузке возникнет исключение <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-137">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="7c7e0-138">Это правило также применяется в том случае, если базовый и производный классы находятся в одной сборке.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-138">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="7c7e0-139">`AllowPartiallyTrustedCallers` (уровень 2 только): Весь код по умолчанию является прозрачным.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-139">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="7c7e0-140">Однако отдельные типы и члены могут иметь другие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-140">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="7c7e0-141">В следующей таблице сравнивается поведение сборки уровня 2 и уровня 1.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-141">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="7c7e0-142">Assembly - атрибут</span><span class="sxs-lookup"><span data-stu-id="7c7e0-142">Assembly attribute</span></span>|<span data-ttu-id="7c7e0-143">Уровень 2</span><span class="sxs-lookup"><span data-stu-id="7c7e0-143">Level 2</span></span>|<span data-ttu-id="7c7e0-144">Уровень 1</span><span class="sxs-lookup"><span data-stu-id="7c7e0-144">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="7c7e0-145">Частично доверенная сборка без атрибутов</span><span class="sxs-lookup"><span data-stu-id="7c7e0-145">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="7c7e0-146">Типы и члены по умолчанию являются прозрачными, но могут быть критическими или надежными с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-146">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="7c7e0-147">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-147">All types and members are transparent.</span></span>|
|<span data-ttu-id="7c7e0-148">Атрибут не указан</span><span class="sxs-lookup"><span data-stu-id="7c7e0-148">No attribute</span></span>|<span data-ttu-id="7c7e0-149">Если атрибут не указан, то определение правил прозрачности выполняется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-149">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="7c7e0-150">Все типы и члены являются критическими с точки зрения безопасности за исключением тех случаев, когда это нарушает правило наследования.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-150">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="7c7e0-151">В сборке с полным доверием (в глобальном кэше сборок или в сборке, для которой полное доверие указано в домене `AppDomain`) все типы являются прозрачными, а члены — надежными с точки зрения безопасности.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-151">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="7c7e0-152">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-152">All types and members are transparent.</span></span>|<span data-ttu-id="7c7e0-153">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-153">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="7c7e0-154">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-154">Not applicable.</span></span>|<span data-ttu-id="7c7e0-155">Все типы и члены являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-155">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="7c7e0-156">Код всех типов в этой сборке является критическим, а остальной код — прозрачным.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-156">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="7c7e0-157">При переопределении виртуального или абстрактного метода или при реализации метода интерфейса следует явным образом пометить этот метод как `SecurityCritical` или `SecuritySafeCritical`.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-157">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="7c7e0-158">Весь код по умолчанию является прозрачным.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-158">All code defaults to transparent.</span></span> <span data-ttu-id="7c7e0-159">Однако отдельные типы и члены могут иметь другие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-159">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="7c7e0-160">Заметки для типов и членов</span><span class="sxs-lookup"><span data-stu-id="7c7e0-160">Type and Member Annotation</span></span>

<span data-ttu-id="7c7e0-161">Атрибуты безопасности, которые применяются к типу, также применяются и к членам, которые представлены этим типом.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-161">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="7c7e0-162">Однако они не применяются к виртуальным или абстрактным переопределениям базового класса, а также к реализациям интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-162">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="7c7e0-163">Ниже перечислены правила, которые применяются к использованию атрибутов на уровне типов и членов.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-163">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="7c7e0-164">`SecurityCritical`: Тип или член является критически важным и может вызываться только полностью доверенный код.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-164">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="7c7e0-165">Методы, представленные в критическом с точки зрения безопасности коде, также являются критическими.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-165">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7c7e0-166">Виртуальные и абстрактные методы, представленные в базовых классах или интерфейсах и переопределяемые или реализуемые в критическом с точки зрения безопасности классе, по умолчанию являются прозрачными.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-166">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="7c7e0-167">Их следует пометить как `SecuritySafeCritical` или `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-167">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="7c7e0-168">`SecuritySafeCritical`: Тип или член является надежным с точки зрения.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-168">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="7c7e0-169">В то же время этот тип или член может вызываться из прозрачного кода (с частичным доверием) и имеет те же возможности, что и любой другой критический код.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-169">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="7c7e0-170">Код необходимо проверить на безопасность.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-170">The code must be audited for security.</span></span>

[<span data-ttu-id="7c7e0-171">К началу</span><span class="sxs-lookup"><span data-stu-id="7c7e0-171">Back to top</span></span>](#top)

<a name="override"></a>

## <a name="override-patterns"></a><span data-ttu-id="7c7e0-172">Схемы переопределения</span><span class="sxs-lookup"><span data-stu-id="7c7e0-172">Override Patterns</span></span>

<span data-ttu-id="7c7e0-173">В таблице ниже представлены разрешенные переопределения метода для прозрачности уровня 2.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-173">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="7c7e0-174">Базовый виртуальный член или член интерфейса</span><span class="sxs-lookup"><span data-stu-id="7c7e0-174">Base virtual/interface member</span></span>|<span data-ttu-id="7c7e0-175">Переопределение или интерфейс</span><span class="sxs-lookup"><span data-stu-id="7c7e0-175">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

[<span data-ttu-id="7c7e0-176">К началу</span><span class="sxs-lookup"><span data-stu-id="7c7e0-176">Back to top</span></span>](#top)

<a name="inheritance"></a>

## <a name="inheritance-rules"></a><span data-ttu-id="7c7e0-177">Правила наследования</span><span class="sxs-lookup"><span data-stu-id="7c7e0-177">Inheritance Rules</span></span>

<span data-ttu-id="7c7e0-178">В этом разделе коду `Transparent`, `Critical` и `SafeCritical` в зависимости от доступа и возможностей присваивается следующий порядок:</span><span class="sxs-lookup"><span data-stu-id="7c7e0-178">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="7c7e0-179">Правила для типов: Движения слева направо, доступ становится более ограниченным.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-179">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="7c7e0-180">Производные типы должны иметь как минимум те же ограничения, что и базовый тип.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-180">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="7c7e0-181">Правила для методов: Производные методы не могут изменять доступность из базового метода.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-181">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="7c7e0-182">По умолчанию все производные методы без заметок являются методами `Transparent`.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-182">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="7c7e0-183">Типы, производные от критических, вызывают возникновение исключения, если переопределенный метод явным образом не помечен как `SecurityCritical`.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-183">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="7c7e0-184">В таблице ниже показаны разрешенные схемы наследования типов.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-184">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="7c7e0-185">Базовый класс</span><span class="sxs-lookup"><span data-stu-id="7c7e0-185">Base class</span></span>|<span data-ttu-id="7c7e0-186">Производный класс может быть</span><span class="sxs-lookup"><span data-stu-id="7c7e0-186">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="7c7e0-187">В таблице ниже показаны запрещенные схемы наследования типов.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-187">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="7c7e0-188">Базовый класс</span><span class="sxs-lookup"><span data-stu-id="7c7e0-188">Base class</span></span>|<span data-ttu-id="7c7e0-189">Производный класс не может быть</span><span class="sxs-lookup"><span data-stu-id="7c7e0-189">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="7c7e0-190">В таблице ниже показаны разрешенные схемы наследования методов.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-190">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="7c7e0-191">Базовый метод</span><span class="sxs-lookup"><span data-stu-id="7c7e0-191">Base method</span></span>|<span data-ttu-id="7c7e0-192">Производный метод может быть</span><span class="sxs-lookup"><span data-stu-id="7c7e0-192">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="7c7e0-193">В таблице ниже показаны запрещенные схемы наследования методов.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-193">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="7c7e0-194">Базовый метод</span><span class="sxs-lookup"><span data-stu-id="7c7e0-194">Base method</span></span>|<span data-ttu-id="7c7e0-195">Производный метод не может быть</span><span class="sxs-lookup"><span data-stu-id="7c7e0-195">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="7c7e0-196">Эти правила наследования применяются к типам и членам уровня 2.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-196">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="7c7e0-197">Типы в сборках уровня 1 могут наследоваться от критических с точки зрения безопасности типов и членов уровня 2.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-197">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="7c7e0-198">Таким образом, типы и члены уровня 2 должны иметь различные требования к наследованию для наследуемых типов и членов уровня 1.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-198">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

[<span data-ttu-id="7c7e0-199">К началу</span><span class="sxs-lookup"><span data-stu-id="7c7e0-199">Back to top</span></span>](#top)

<a name="additional"></a>

## <a name="additional-information-and-rules"></a><span data-ttu-id="7c7e0-200">Дополнительные сведения и правила</span><span class="sxs-lookup"><span data-stu-id="7c7e0-200">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="7c7e0-201">Поддержка LinkDemand</span><span class="sxs-lookup"><span data-stu-id="7c7e0-201">LinkDemand Support</span></span>

<span data-ttu-id="7c7e0-202">Модель прозрачности уровня 2 заменяет <xref:System.Security.Permissions.SecurityAction.LinkDemand> атрибутом <xref:System.Security.SecurityCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-202">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="7c7e0-203">В устаревшем коде (уровень 1) <xref:System.Security.Permissions.SecurityAction.LinkDemand> автоматически рассматривается как <xref:System.Security.Permissions.SecurityAction.Demand>.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-203">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="7c7e0-204">Отражение</span><span class="sxs-lookup"><span data-stu-id="7c7e0-204">Reflection</span></span>

<span data-ttu-id="7c7e0-205">Вызов критического метода или чтение критического поля вызывает требование полного доверия (как при вызове закрытого метода или поля).</span><span class="sxs-lookup"><span data-stu-id="7c7e0-205">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="7c7e0-206">Таким образом, критический метод может вызываться только в коде с полным доверием, а не в коде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-206">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="7c7e0-207">В пространство имен <xref:System.Reflection> добавлены следующие свойства, позволяющие определить, является ли тип, метод или поле `SecurityCritical`, `SecuritySafeCritical` или `SecurityTransparent`: <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> и <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-207">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="7c7e0-208">Используйте эти свойства, чтобы определить прозрачность с помощью отражения, вместо проверки присутствия атрибута.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-208">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="7c7e0-209">Правила прозрачности достаточно сложны, и проверки существования атрибута может быть недостаточно.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-209">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="7c7e0-210">Объект `SafeCritical` возвращает `true` для обоих <xref:System.Type.IsSecurityCritical%2A> и <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, так как `SafeCritical` действительно является критическим (имеет те же возможности, что и критический код, но может вызываться из прозрачного кода).</span><span class="sxs-lookup"><span data-stu-id="7c7e0-210">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="7c7e0-211">Динамические методы наследуют прозрачность модулей, к которым они присоединены. Они не наследуют прозрачность типа (если они присоединены к типу).</span><span class="sxs-lookup"><span data-stu-id="7c7e0-211">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="7c7e0-212">Пропуск проверки при полном доверии</span><span class="sxs-lookup"><span data-stu-id="7c7e0-212">Skip Verification in Full Trust</span></span>

<span data-ttu-id="7c7e0-213">Для прозрачных сборок с полным доверием проверку можно пропустить, установив свойство <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> равным `true` в атрибуте <xref:System.Security.SecurityRulesAttribute>:</span><span class="sxs-lookup"><span data-stu-id="7c7e0-213">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="7c7e0-214">Свойство <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> по умолчанию равно `false`, поэтому для пропуска проверки его нужно установить равным `true`.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-214">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="7c7e0-215">Это следует делать только в целях оптимизации.</span><span class="sxs-lookup"><span data-stu-id="7c7e0-215">This should be done for optimization purposes only.</span></span> <span data-ttu-id="7c7e0-216">Следует убедиться, что прозрачный код в сборке проверяемые с помощью `transparent` в диалоговом окне [средство PEVerify](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span><span class="sxs-lookup"><span data-stu-id="7c7e0-216">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c7e0-217">См. также</span><span class="sxs-lookup"><span data-stu-id="7c7e0-217">See also</span></span>

- [<span data-ttu-id="7c7e0-218">Прозрачный с точки зрения безопасности код, уровень 1</span><span class="sxs-lookup"><span data-stu-id="7c7e0-218">Security-Transparent Code, Level 1</span></span>](../../../docs/framework/misc/security-transparent-code-level-1.md)
- [<span data-ttu-id="7c7e0-219">Изменения системы безопасности</span><span class="sxs-lookup"><span data-stu-id="7c7e0-219">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)
