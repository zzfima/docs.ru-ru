---
title: по безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: a3debf487b9b2a04277d9ce3007f28662fa4899e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734501"
---
# <a name="windows-forms-security"></a><span data-ttu-id="db26c-102">Безопасность Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db26c-102">Windows Forms Security</span></span>
<span data-ttu-id="db26c-103">Windows Forms содержит модель безопасности, основанную на коде (уровни безопасности задаются для кода, независимо от пользователя, запустившего код).</span><span class="sxs-lookup"><span data-stu-id="db26c-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="db26c-104">Это дополнение к схемам безопасности, которые могут быть уже установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="db26c-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="db26c-105">К ним могут относиться данные в браузере (например, безопасность на основе зоны, доступная в Internet Explorer) или операционная система (например, безопасность на основе учетных данных Windows NT).</span><span class="sxs-lookup"><span data-stu-id="db26c-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db26c-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="db26c-106">In This Section</span></span>  
 [<span data-ttu-id="db26c-107">Общие сведения о безопасности в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db26c-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="db26c-108">Краткое описание модели безопасности .NET Framework и основных действий, необходимых для обеспечения безопасности Windows Forms в приложении.</span><span class="sxs-lookup"><span data-stu-id="db26c-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="db26c-109">Более безопасный доступ к файлам и данным в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db26c-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="db26c-110">Описывает, как получить доступ к файлам и данным в среде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="db26c-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="db26c-111">Более безопасная печать в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db26c-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="db26c-112">Описание способов доступа к функциям печати в частично доверяемой среде.</span><span class="sxs-lookup"><span data-stu-id="db26c-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="db26c-113">Дополнительные вопросы безопасности в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db26c-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="db26c-114">Описывает выполнение операций с окнами, использование буфера обмена и вызов неуправляемого кода в среде с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="db26c-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="db26c-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="db26c-115">Related Sections</span></span>  
 <span data-ttu-id="db26c-116">[Политика безопасности по умолчанию](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="db26c-116">[Default Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="db26c-117">Список разрешений по умолчанию, предоставленных в наборах разрешений «полное доверие», «Местная интрасеть» и «Интернет».</span><span class="sxs-lookup"><span data-stu-id="db26c-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="db26c-118">[Общее администрирование политики безопасности](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="db26c-118">[General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="db26c-119">Содержит сведения об администрировании политики безопасности .NET Framework и повышении разрешений.</span><span class="sxs-lookup"><span data-stu-id="db26c-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="db26c-120">Опасные разрешения и администрирование политик</span><span class="sxs-lookup"><span data-stu-id="db26c-120">Dangerous Permissions and Policy Administration</span></span>](../misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="db26c-121">Обсуждаются некоторые разрешения the.NET Framework, которые потенциально позволяют обойти систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="db26c-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="db26c-122">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="db26c-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="db26c-123">Ссылки на разделы, в которых объясняются рекомендации по безопасному написанию кода для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db26c-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="db26c-124">[Запрос разрешений](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="db26c-124">[Requesting Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="db26c-125">Обсуждается использование атрибутов для того, чтобы среда выполнения знала, какие разрешения необходимо выполнить коду.</span><span class="sxs-lookup"><span data-stu-id="db26c-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="db26c-126">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="db26c-126">Key Security Concepts</span></span>](../../standard/security/key-security-concepts.md)  
 <span data-ttu-id="db26c-127">Ссылки на разделы, посвященные основным аспектам безопасности кода.</span><span class="sxs-lookup"><span data-stu-id="db26c-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="db26c-128">Основы управления доступом для кода</span><span class="sxs-lookup"><span data-stu-id="db26c-128">Code Access Security Basics</span></span>](../misc/code-access-security-basics.md)  
 <span data-ttu-id="db26c-129">Описывает основные принципы работы с политикой безопасности .NET Framework времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="db26c-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="db26c-130">[Определение необходимости изменения политики безопасности](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="db26c-130">[Determining When to Modify Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="db26c-131">В этой статье объясняется, как определить, когда приложения должны рассогласовановать с политикой безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db26c-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="db26c-132">[Развертывание политики безопасности](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="db26c-132">[Deploying Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="db26c-133">Описание оптимального способа развертывания изменений в политике безопасности.</span><span class="sxs-lookup"><span data-stu-id="db26c-133">Discusses the best manner for deploying security policy changes.</span></span>
