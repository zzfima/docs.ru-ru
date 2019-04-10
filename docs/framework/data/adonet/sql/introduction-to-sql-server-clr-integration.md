---
title: Знакомство с интеграцией CLR в SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: dc7d19bf361ed5fcda1fd5edf64eeb5e4ce15a71
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336815"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="02d88-102">Знакомство с интеграцией CLR в SQL Server</span><span class="sxs-lookup"><span data-stu-id="02d88-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="02d88-103">Среда CLR является сердцем платформы Microsoft .NET Framework и предоставляет среду выполнения для всего кода .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02d88-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="02d88-104">Код, выполняемый в среде CLR, называется управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="02d88-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="02d88-105">Среда CLR предоставляет различные функции и услуги, требуемые для выполнения программы, включая JIT-компиляцию, распределение и управление памятью, соблюдение безопасности типов, обработку исключений, управление потоками и безопасность.</span><span class="sxs-lookup"><span data-stu-id="02d88-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="02d88-106">Если среда CLR размещается в Microsoft SQL Server (что принято называть интеграцией со средой CLR), то появляется возможность разрабатывать в управляемом коде хранимые процедуры, триггеры, определяемые пользователем функции, определяемые пользователем типы и определяемые пользователем агрегатные функции.</span><span class="sxs-lookup"><span data-stu-id="02d88-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="02d88-107">Из-за того, что управляемый код перед выполнением производит компиляцию в машинный код, можно достичь значительного увеличения производительности в некоторых сценариях.</span><span class="sxs-lookup"><span data-stu-id="02d88-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="02d88-108">В управляемом коде используются управление доступом для кода (CAS), ссылки на код и домены приложений для предотвращения выполнения сборками определенных операций.</span><span class="sxs-lookup"><span data-stu-id="02d88-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="02d88-109">В SQL Server используется CAS для обеспечения безопасности управляемого кода и предотвращения нарушений безопасности операционной системы или сервера баз данных.</span><span class="sxs-lookup"><span data-stu-id="02d88-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="02d88-110">Этот раздел предназначен для предоставления лишь такого количества сведений, с которого можно приступать к программированию в рамках интеграции SQL Server со средой CLR, и не рассчитан на всестороннее изложение.</span><span class="sxs-lookup"><span data-stu-id="02d88-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="02d88-111">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02d88-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="02d88-112">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="02d88-112">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="02d88-113">Общие сведения об интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-113">Common Language Runtime (CLR) Integration Overview</span></span>](https://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="02d88-114">Включение интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="02d88-115">Возможность интеграции со средой CLR отключена в Microsoft SQL Server по умолчанию, поэтому ее нужно включить, чтобы использовать объекты, использующие интеграцию со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="02d88-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="02d88-116">Чтобы включить интеграцию со средой CLR с помощью Transact-SQL, воспользуйтесь параметром `clr enabled` хранимой процедуры `sp_configure`, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="02d88-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="02d88-117">Интеграцию со средой CLR можно отключить, присвоив параметру `clr enabled` значение 0.</span><span class="sxs-lookup"><span data-stu-id="02d88-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="02d88-118">При этом SQL Server прекращает выполнять все процедуры CLR и выгружает все домены приложений.</span><span class="sxs-lookup"><span data-stu-id="02d88-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="02d88-119">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02d88-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="02d88-120">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="02d88-120">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="02d88-121">Включение интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-121">Enabling CLR Integration</span></span>](https://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="02d88-122">Развертывание сборки среды CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="02d88-123">После тестирования методов среды CLR и проверки на тестовом сервере их можно установить на рабочие серверы с помощью скриптов развертывания.</span><span class="sxs-lookup"><span data-stu-id="02d88-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="02d88-124">Скриптов развертывания можно создать вручную или с помощью SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="02d88-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="02d88-125">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02d88-125">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="02d88-126">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="02d88-126">SQL Server Books Online</span></span>**  
  
1. [<span data-ttu-id="02d88-127">Развертывание объектов базы данных CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-127">Deploying CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="02d88-128">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-128">CLR Integration Security</span></span>  
 <span data-ttu-id="02d88-129">Интеграция модели безопасности Microsoft SQL Server со средой Microsoft .NET Framework CLR позволяет поддерживать доступ для различных типов объектов (как CLR, так и не CLR), выполняемых в SQL Server, а также обеспечивать безопасность этого доступа.</span><span class="sxs-lookup"><span data-stu-id="02d88-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="02d88-130">Для вызова этих объектов может применяться инструкция Transact-SQL или другой объект CLR, выполняемый на сервере.</span><span class="sxs-lookup"><span data-stu-id="02d88-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="02d88-131">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02d88-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="02d88-132">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="02d88-132">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="02d88-133">Безопасность интеграции со средой CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-133">CLR Integration Security</span></span>](https://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="02d88-134">Отладка сборки CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="02d88-135">В Microsoft SQL Server предоставляется поддержка для отладки кода Transact-SQL и объектов среды CLR в базе данных.</span><span class="sxs-lookup"><span data-stu-id="02d88-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="02d88-136">Процесс отладки работает с кодом на всех используемых языках: пользователи могут беспрепятственно переходить к коду объектов среды CLR из кода Transact-SQL и наоборот.</span><span class="sxs-lookup"><span data-stu-id="02d88-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="02d88-137">Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02d88-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="02d88-138">Электронная документация по SQL Server</span><span class="sxs-lookup"><span data-stu-id="02d88-138">SQL Server Books Online</span></span>**  
  
-   [<span data-ttu-id="02d88-139">Отладка объектов баз данных CLR</span><span class="sxs-lookup"><span data-stu-id="02d88-139">Debugging CLR Database Objects</span></span>](https://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a><span data-ttu-id="02d88-140">См. также</span><span class="sxs-lookup"><span data-stu-id="02d88-140">See also</span></span>

- [<span data-ttu-id="02d88-141">Управление доступом для кода и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="02d88-141">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)
- [<span data-ttu-id="02d88-142">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="02d88-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
