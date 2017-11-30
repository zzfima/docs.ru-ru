---
title: "Использование библиотек из не вполне надежного кода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a452370df7c18f3e3f0190a14979099152485f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-libraries-from-partially-trusted-code"></a><span data-ttu-id="18de6-102">Использование библиотек из не вполне надежного кода</span><span class="sxs-lookup"><span data-stu-id="18de6-102">Using Libraries from Partially Trusted Code</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
>  <span data-ttu-id="18de6-103">Этот раздел описывает поведение сборок со строгими именами и применяется только к [уровня 1](../../../docs/framework/misc/security-transparent-code-level-1.md) сборки.</span><span class="sxs-lookup"><span data-stu-id="18de6-103">This topic addresses the behavior of strong-named assemblies and applies only to [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) assemblies.</span></span> <span data-ttu-id="18de6-104">[Прозрачный с точки зрения безопасности код, уровень 2](../../../docs/framework/misc/security-transparent-code-level-2.md) сборок в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] или более поздних версий не зависят от строгих имен.</span><span class="sxs-lookup"><span data-stu-id="18de6-104">[Security-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) assemblies in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later are not affected by strong names.</span></span> <span data-ttu-id="18de6-105">Дополнительные сведения об изменениях системы безопасности см. в разделе [изменения системы безопасности](../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="18de6-105">For more information about changes to the security system, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="18de6-106">Приложения, которые получают меньше, чем полное доверие со стороны узла или песочницы не могут вызывать Общие управляемые библиотеки, если только автор библиотеки разрешил это специально для использования <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="18de6-106">Applications that receive less than full trust from their host or sandbox are not allowed to call shared managed libraries unless the library writer specifically allows them to through the use of the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="18de6-107">Таким образом, авторы приложений должны иметь в виду, что некоторые библиотеки будут им недоступны в контексте частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="18de6-107">Therefore, application writers must be aware that some libraries will not be available to them from a partially trusted context.</span></span> <span data-ttu-id="18de6-108">По умолчанию весь код, выполняемый в частично доверенной ["песочницы"](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) и не входящий в список сборок с полным доверием, имеет частичное доверие.</span><span class="sxs-lookup"><span data-stu-id="18de6-108">By default, all code that executes in a partial-trust [sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) and is not in the list of full-trust assemblies is partially trusted.</span></span> <span data-ttu-id="18de6-109">Если не предполагается, что код будет запускаться в частично доверенном контексте или вызываться кодом с частичным доверием, данный раздел можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="18de6-109">If you do not expect your code to be executed from a partially trusted context or to be called by partially trusted code, you do not have to be concerned about the information in this section.</span></span> <span data-ttu-id="18de6-110">Однако при написании кода, который должен взаимодействовать с частично доверенным кодом или работать из частично доверенного контекста, следует учитывать следующие факторы.</span><span class="sxs-lookup"><span data-stu-id="18de6-110">However, if you write code that must interact with partially trusted code or operate from a partially trusted context, you should consider the following factors:</span></span>  
  
-   <span data-ttu-id="18de6-111">Библиотеки должны быть подписаны строгим именем, чтобы их могли совместно использовать несколько приложений.</span><span class="sxs-lookup"><span data-stu-id="18de6-111">Libraries must be signed with a strong name in order to be shared by multiple applications.</span></span> <span data-ttu-id="18de6-112">Строгие имена позволяют помещать код в глобальный кэш сборок или добавлять его в список полного доверия песочницы <xref:System.AppDomain>, а также позволяют потребителям удостовериться, что данный фрагмент мобильного кода действительно исходит от вас.</span><span class="sxs-lookup"><span data-stu-id="18de6-112">Strong names allow your code to be placed in the global assembly cache or added to the full-trust list of a sandboxing <xref:System.AppDomain>, and allow consumers to verify that a particular piece of mobile code actually originates from you.</span></span>  
  
-   <span data-ttu-id="18de6-113">По умолчанию со строгими именами [уровня 1](../../../docs/framework/misc/security-transparent-code-level-1.md) общие библиотеки выполняют неявную [LinkDemand](../../../docs/framework/misc/link-demands.md) для полного доверия автоматически, не требуя никаких действий от автора библиотеки.</span><span class="sxs-lookup"><span data-stu-id="18de6-113">By default, strong-named [Level 1](../../../docs/framework/misc/security-transparent-code-level-1.md) shared libraries perform an implicit [LinkDemand](../../../docs/framework/misc/link-demands.md) for full trust automatically, without the library writer having to do anything.</span></span>  
  
-   <span data-ttu-id="18de6-114">Если вызывающий объект не имеет полного доверия, однако пытается вызывать такую библиотеку, среда выполнения создает <xref:System.Security.SecurityException>, а вызывающему объекту запрещается связь с библиотекой.</span><span class="sxs-lookup"><span data-stu-id="18de6-114">If a caller does not have full trust but still tries to call such a library, the runtime throws a <xref:System.Security.SecurityException> and the caller is not allowed to link to the library.</span></span>  
  
-   <span data-ttu-id="18de6-115">Чтобы отключить автоматическое **LinkDemand** и предотвратить возникновение исключения, можно поместить **AllowPartiallyTrustedCallersAttribute** атрибут в области действия сборки общей Библиотека.</span><span class="sxs-lookup"><span data-stu-id="18de6-115">In order to disable the automatic **LinkDemand** and prevent the exception from being thrown, you can place the **AllowPartiallyTrustedCallersAttribute** attribute on the assembly scope of a shared library.</span></span> <span data-ttu-id="18de6-116">Этот атрибут позволяет вызывать библиотеки из частично доверенного управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="18de6-116">This attribute allows your libraries to be called from partially trusted managed code.</span></span>  
  
-   <span data-ttu-id="18de6-117">На частично доверенный код, получающий доступ к библиотеке при помощи этого атрибута, по-прежнему налагаются дополнительные ограничения, определяемые <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="18de6-117">Partially trusted code that is granted access to a library with this attribute is still subject to further restrictions defined by the <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="18de6-118">Нет программные возможности для частично доверенного кода для вызова библиотеки, которая не имеет **AllowPartiallyTrustedCallersAttribute** атрибута.</span><span class="sxs-lookup"><span data-stu-id="18de6-118">There is no programmatic way for partially trusted code to call a library that does not have the **AllowPartiallyTrustedCallersAttribute** attribute.</span></span>  
  
 <span data-ttu-id="18de6-119">Библиотеки, являющиеся собственными для определенного приложения не требуют строгого имени или **AllowPartiallyTrustedCallersAttribute** атрибута и не может ссылаться потенциально вредоносный код извне приложения.</span><span class="sxs-lookup"><span data-stu-id="18de6-119">Libraries that are private to a specific application do not require a strong name or the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be referenced by potentially malicious code outside the application.</span></span> <span data-ttu-id="18de6-120">Такой код защищен от преднамеренного или непреднамеренного неправильного использования со стороны мобильного кода с частичным доверием, и никаких дополнительных действий со стороны разработчика не требуется.</span><span class="sxs-lookup"><span data-stu-id="18de6-120">Such code is protected against intentional or unintentional misuse by partially trusted mobile code without the developer having to do anything extra.</span></span>  
  
 <span data-ttu-id="18de6-121">Рекомендуется явно разрешить использование частично доверенным кодом для следующих типов кода.</span><span class="sxs-lookup"><span data-stu-id="18de6-121">You should consider explicitly enabling use by partially trusted code for the following types of code:</span></span>  
  
-   <span data-ttu-id="18de6-122">Код, который был тщательно протестирован на наличие уязвимостей безопасности и соответствует рекомендациям, приведенным в [правила написания безопасного кода](../../../docs/standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="18de6-122">Code that has been diligently tested for security vulnerabilities and is in compliance with the guidelines described in [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md).</span></span>  
  
-   <span data-ttu-id="18de6-123">Строго именованные библиотеки кода, специально написанные для частично доверенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="18de6-123">Strong-named code libraries that are specifically written for partially trusted scenarios.</span></span>  
  
-   <span data-ttu-id="18de6-124">Все компоненты (с частичным или полным доверием), подписанные строгим именем, которые будут вызываться кодом, скачанным из Интернета.</span><span class="sxs-lookup"><span data-stu-id="18de6-124">Any components (whether partially or fully trusted) signed with a strong name that will be called by code that is downloaded from the Internet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18de6-125">Некоторые классы в библиотеке классов .NET Framework не имеют **AllowPartiallyTrustedCallersAttribute** атрибута и не могут вызываться частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="18de6-125">Some classes in the .NET Framework class library do not have the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be called by partially trusted code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18de6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="18de6-126">See Also</span></span>  
 [<span data-ttu-id="18de6-127">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="18de6-127">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
