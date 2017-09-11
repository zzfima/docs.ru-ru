---
title: "Безопасность в .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- .NET Framework, security
- security [.NET Framework], about security
- application development [.NET Framework], security
- security [.NET Framework]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
caps.latest.revision: 37
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b2c487c76a6a0b42370b7b70099d5baba58f42db
ms.contentlocale: ru-ru
ms.lasthandoff: 09/05/2017

---
# <a name="security-in-the-net-framework"></a><span data-ttu-id="7e098-102">Безопасность в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7e098-102">Security in the .NET Framework</span></span>
<span data-ttu-id="7e098-103">Среда CLR и платформа .NET Framework предоставляют много полезных классов и служб, которые позволяют разработчикам легко создавать безопасный код, а администраторам — настраивать разрешения для кода, чтобы из кода можно было осуществлять доступ к защищенным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="7e098-103">The common language runtime and the .NET Framework provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="7e098-104">Кроме того, среда выполнения и платформа .NET Framework предоставляют полезные классы и службы, позволяющие использовать шифрование и безопасность на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="7e098-104">In addition, the runtime and the .NET Framework provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e098-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="7e098-105">In This Section</span></span>  
 [<span data-ttu-id="7e098-106">Изменения системы безопасности</span><span class="sxs-lookup"><span data-stu-id="7e098-106">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)  
 <span data-ttu-id="7e098-107">Описываются важные изменения в системе безопасности .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e098-107">Describes important changes to the .NET Framework security system.</span></span>  
  
 [<span data-ttu-id="7e098-108">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="7e098-108">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="7e098-109">Обзор функций безопасности среды CLR.</span><span class="sxs-lookup"><span data-stu-id="7e098-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="7e098-110">Этот раздел представляет интерес для разработчиков и системных администраторов.</span><span class="sxs-lookup"><span data-stu-id="7e098-110">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="7e098-111">Безопасность на основе ролей</span><span class="sxs-lookup"><span data-stu-id="7e098-111">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="7e098-112">Описывается взаимодействие кода с системой безопасности на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="7e098-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="7e098-113">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="7e098-113">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="7e098-114">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="7e098-114">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="7e098-115">Обзор служб шифрования, предоставляемых платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e098-115">Provides an overview of cryptographic services provided by the .NET Framework.</span></span> <span data-ttu-id="7e098-116">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="7e098-116">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="7e098-117">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="7e098-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="7e098-118">Описываются некоторые передовые методики создания надежных приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e098-118">Describes some of the best practices for creating reliable .NET Framework applications.</span></span> <span data-ttu-id="7e098-119">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="7e098-119">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="7e098-120">Руководства по написанию безопасного неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="7e098-120">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="7e098-121">Описывает некоторые рекомендации и аспекты безопасности при вызове неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="7e098-121">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="7e098-122">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="7e098-122">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="7e098-123">Описывается реализация удостоверений на основе утверждений в приложениях.</span><span class="sxs-lookup"><span data-stu-id="7e098-123">Describes how you can implement claims-based identity in your applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7e098-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7e098-124">Related Sections</span></span>  
 [<span data-ttu-id="7e098-125">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="7e098-125">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="7e098-126">Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.</span><span class="sxs-lookup"><span data-stu-id="7e098-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

