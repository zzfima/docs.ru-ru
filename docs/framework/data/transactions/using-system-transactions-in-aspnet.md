---
title: Использование инфраструктуры System.Transactions в среде ASP.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fff55f6177a50d05f54c8839fd3497c181290ecf
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="0532a-102">Использование инфраструктуры System.Transactions в среде ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0532a-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="0532a-103">В этом разделе описывается, как можно эффективно использовать пространство имен <xref:System.Transactions> в приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0532a-103">This topic describes how you can successfully use <xref:System.Transactions> inside an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="0532a-104">Включение разрешения DistributedTransactionPermission в ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0532a-104">Enable DistributedTransactionPermission in ASP.NET</span></span>  
 <span data-ttu-id="0532a-105"><xref:System.Transactions> поддерживает частично доверенных вызывающих и отмечена атрибутом **AllowPartiallyTrustedCallers** (APTCA).</span><span class="sxs-lookup"><span data-stu-id="0532a-105"><xref:System.Transactions> supports partially trusted callers and is marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="0532a-106">Уровни доверия для сборки <xref:System.Transactions> определяются на основе типов ресурсов (например, системная память, ресурсы, общие для всего процесса, ресурсы, общие для всей системы, и другие ресурсы), которые используются в <xref:System.Transactions> , и уровня доверия, необходимого для доступа к этим ресурсам.</span><span class="sxs-lookup"><span data-stu-id="0532a-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources, (for example, system memory, shared process-wide resources, system-wide resources, and other resources), that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="0532a-107">В среде с частичным доверием сборка с неполным доверием может использовать только транзакции внутри домена приложения (в этом случае единственным защищаемым ресурсом является системная память), пока этой сборке не будет предоставлено разрешение <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="0532a-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>  
  
 <span data-ttu-id="0532a-108">Разрешение<xref:System.Transactions.DistributedTransactionPermission> запрашивается при каждой передаче управления транзакцией координатору распределенных транзакций (Майкрософт) (MSDTC).</span><span class="sxs-lookup"><span data-stu-id="0532a-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="0532a-109">В этом сценарии используются ресурсы, общие для всего процесса, и прежде всего один глобальный ресурс, зарезервированный в журнале MSDTC,</span><span class="sxs-lookup"><span data-stu-id="0532a-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="0532a-110">например внешнее веб-приложение для взаимодействия с базой данных или приложение, использующее базу данных в рамках предоставляемых им служб.</span><span class="sxs-lookup"><span data-stu-id="0532a-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="0532a-111"> имеет собственный набор уровней доверия, с которыми при помощи файлов политики связан определенный набор разрешений.</span><span class="sxs-lookup"><span data-stu-id="0532a-111"> has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> <span data-ttu-id="0532a-112">Дополнительные сведения см. в разделе [ASP.NET уровни доверия и файлы политики](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span><span class="sxs-lookup"><span data-stu-id="0532a-112">For more information, see [ASP.NET Trust Levels and Policy Files](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span></span> <span data-ttu-id="0532a-113">После первоначальной установки пакета Windows SDK ни один из файлов политики [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] по умолчанию не связан с разрешением <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="0532a-113">When you initially install the Windows SDK, none of the default [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="0532a-114">Поэтому передачу управления транзакцией приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] координатору MSDTC выполнить не удается: возникает исключение <xref:System.Security.SecurityException> при запросе разрешения <xref:System.Transactions.DistributedTransactionPermission>.</span><span class="sxs-lookup"><span data-stu-id="0532a-114">As such, when your transaction in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="0532a-115">Чтобы обеспечить передачу транзакции на следующий уровень иерархии среды [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] с частичным уровнем доверия, необходимо предоставить разрешение <xref:System.Transactions.DistributedTransactionPermission> для уровней доверия по умолчанию, у которых есть разрешение <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="0532a-115">To enable transaction escalation in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="0532a-116">Можно настроить пользовательский уровень доверия и файл политики для его поддержки или изменить файлы политики по умолчанию **Web_hightrust.config** и **Web_mediumtrust.config**.</span><span class="sxs-lookup"><span data-stu-id="0532a-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>  
  
 <span data-ttu-id="0532a-117">Чтобы изменить файлы политики, добавьте **SecurityClass** элемент для **разрешения DistributedTransactionPermission** для **SecurityClasses** элемента под  **Сохранить** элемент и добавьте соответствующий **IPermission** элемента под [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** для System.Transactions.</span><span class="sxs-lookup"><span data-stu-id="0532a-117">To modify the policy files, add a **SecurityClass** element for **DistributedTransactionPermission** to the **SecurityClasses** element under the **PolicyLevel** element and add a corresponding **IPermission** element under the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** for System.Transactions.</span></span> <span data-ttu-id="0532a-118">Это показано в следующем файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0532a-118">The following configuration file demonstrates this.</span></span>  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 <span data-ttu-id="0532a-119">Дополнительные сведения о [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] политики безопасности в разделе [элемент securityPolicy (схема параметров ASP.NET)](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba).</span><span class="sxs-lookup"><span data-stu-id="0532a-119">For more information about [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] security policy, see [securityPolicy Element (ASP.NET Settings Schema)](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba).</span></span>  
  
## <a name="dynamic-compilation"></a><span data-ttu-id="0532a-120">Динамическая компиляция</span><span class="sxs-lookup"><span data-stu-id="0532a-120">Dynamic Compilation</span></span>  
 <span data-ttu-id="0532a-121">Чтобы импортировать и использовать <xref:System.Transactions> в приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , динамически компилируемом во время доступа, в файле конфигурации необходимо указать ссылку на сборку <xref:System.Transactions> .</span><span class="sxs-lookup"><span data-stu-id="0532a-121">If you want to import and use <xref:System.Transactions> in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="0532a-122">В частности, ссылку необходимо добавить в раздел **compilation**/**assemblies** корневого файла конфигурации по умолчанию **Web.config** или файла конфигурации конкретного веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="0532a-122">Specifically, the reference should be added under the **compilation**/**assemblies** section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="0532a-123">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="0532a-123">The following example demonstrates this.</span></span>  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 <span data-ttu-id="0532a-124">Дополнительные сведения см. в разделе [добавьте элемент для сборки для компиляции (схема параметров ASP.NET)](http://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4).</span><span class="sxs-lookup"><span data-stu-id="0532a-124">For more information, see [add Element for assemblies for compilation (ASP.NET Settings Schema)](http://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0532a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0532a-125">See Also</span></span>  
 [<span data-ttu-id="0532a-126">Уровни доверия ASP.NET и файлы политики</span><span class="sxs-lookup"><span data-stu-id="0532a-126">ASP.NET Trust Levels and Policy Files</span></span>](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [<span data-ttu-id="0532a-127">Элемент securityPolicy (схема параметров ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="0532a-127">securityPolicy Element (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)  
 [<span data-ttu-id="0532a-128">Передача управления транзакцией на следующий уровень иерархии</span><span class="sxs-lookup"><span data-stu-id="0532a-128">Transaction Management Escalation</span></span>](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
