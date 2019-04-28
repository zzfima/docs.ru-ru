---
title: Безопасность в .NET
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e60f463d5a691cb84a30c169e471aa905b2db17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860559"
---
# <a name="security-in-net"></a><span data-ttu-id="85dcb-102">Безопасность в .NET</span><span class="sxs-lookup"><span data-stu-id="85dcb-102">Security in .NET</span></span>
<span data-ttu-id="85dcb-103">Среда CLR и .NET предоставляют много полезных классов и служб, которые позволяют разработчикам написание безопасного кода и позволяют системным администраторам настраивать разрешения для кода можно получить доступ к защищенным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="85dcb-103">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="85dcb-104">Кроме того среда выполнения и .NET предоставляют полезные классы и службами, которые облегчают использование криптографии и безопасности на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="85dcb-104">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="85dcb-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="85dcb-105">In This Section</span></span>  

 [<span data-ttu-id="85dcb-106">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="85dcb-106">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="85dcb-107">Обзор функций безопасности среды CLR.</span><span class="sxs-lookup"><span data-stu-id="85dcb-107">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="85dcb-108">Этот раздел представляет интерес для разработчиков и системных администраторов.</span><span class="sxs-lookup"><span data-stu-id="85dcb-108">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="85dcb-109">Безопасность на основе ролей</span><span class="sxs-lookup"><span data-stu-id="85dcb-109">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="85dcb-110">Описывается взаимодействие кода с системой безопасности на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="85dcb-110">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="85dcb-111">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="85dcb-111">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="85dcb-112">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="85dcb-112">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="85dcb-113">Обзор служб шифрования, предоставляемые .NET.</span><span class="sxs-lookup"><span data-stu-id="85dcb-113">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="85dcb-114">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="85dcb-114">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="85dcb-115">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="85dcb-115">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="85dcb-116">Здесь описываются некоторые рекомендации по созданию надежных приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="85dcb-116">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="85dcb-117">Этот раздел представляет интерес для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="85dcb-117">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="85dcb-118">Руководства по написанию безопасного неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="85dcb-118">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="85dcb-119">Описывает некоторые рекомендации и аспекты безопасности при вызове неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="85dcb-119">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="85dcb-120">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="85dcb-120">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="85dcb-121">Описывается реализация удостоверений на основе утверждений в приложениях.</span><span class="sxs-lookup"><span data-stu-id="85dcb-121">Describes how you can implement claims-based identity in your applications.</span></span>  

<span data-ttu-id="85dcb-122">[Изменения системы безопасности](../../../docs/framework/security/security-changes.md) описываются важные изменения в системе безопасности .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85dcb-122">[Security Changes](../../../docs/framework/security/security-changes.md) Describes important changes to the .NET Framework security system.</span></span>

## <a name="related-sections"></a><span data-ttu-id="85dcb-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="85dcb-123">Related Sections</span></span>  
 [<span data-ttu-id="85dcb-124">Руководство по разработке</span><span class="sxs-lookup"><span data-stu-id="85dcb-124">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="85dcb-125">Здесь содержится руководство по всем ключевым технологическим областям и задачам для разработки приложений, включая создание, настройку, отладку, безопасность и развертывание приложений, а также сведения о динамическом программировании, взаимодействии, расширении среды, управлении памятью и работе с потоками.</span><span class="sxs-lookup"><span data-stu-id="85dcb-125">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
