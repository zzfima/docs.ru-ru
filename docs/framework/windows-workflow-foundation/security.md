---
title: "Безопасность"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a17b77293d9a12fd3720fc54cb6c17a28a8c6ed0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="security"></a><span data-ttu-id="db9a2-102">Безопасность</span><span class="sxs-lookup"><span data-stu-id="db9a2-102">Security</span></span>
<span data-ttu-id="db9a2-103">Хранилище экземпляров рабочих процессов SQL использует следующие роли безопасности базы данных для обеспечения безопасного доступа к сведениям о состоянии экземпляров в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="db9a2-103">The SQL Workflow Instance Store uses the following database security roles to secure access to instance state information in the persistence database.</span></span>  
  
-   <span data-ttu-id="db9a2-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span><span class="sxs-lookup"><span data-stu-id="db9a2-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span></span> <span data-ttu-id="db9a2-105">Эта роль имеет доступ на чтение и запись для всех открытых представлений и права на выполнение хранимых процедур, участвующих в создании, загрузке и сохранении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="db9a2-105">This role has read and write access to public views and execution rights to stored procedures that are involved in creating, loading and saving instances.</span></span>  
  
-   <span data-ttu-id="db9a2-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span><span class="sxs-lookup"><span data-stu-id="db9a2-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span></span> <span data-ttu-id="db9a2-107">Эта роль имеет доступ только для чтения открытых представлений.</span><span class="sxs-lookup"><span data-stu-id="db9a2-107">This role has read-only access to public views.</span></span>  
  
-   <span data-ttu-id="db9a2-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span><span class="sxs-lookup"><span data-stu-id="db9a2-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span></span> <span data-ttu-id="db9a2-109">Эта роль имеет права на выполнение хранимых процедур, участвующих в процессе активации экземпляра.</span><span class="sxs-lookup"><span data-stu-id="db9a2-109">This role has execution rights to stored procedures that are involved in the instance activation process.</span></span> <span data-ttu-id="db9a2-110">Дополнительные сведения об активации экземпляра см. в разделе [активации экземпляра](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span><span class="sxs-lookup"><span data-stu-id="db9a2-110">For more information about instance activation, see [Instance Activation](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span></span> <span data-ttu-id="db9a2-111">Учетная запись пользователя, в которой выполняется универсальное ведущее приложение (например, служба управления рабочего процесса для [!INCLUDE[dublin](../../../includes/dublin-md.md)]), должна быть добавлена к этой роли базы данных.</span><span class="sxs-lookup"><span data-stu-id="db9a2-111">The user account under which a generic host (such as the Workflow Management Service of [!INCLUDE[dublin](../../../includes/dublin-md.md)]) runs should be added to this database role.</span></span>  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="db9a2-112">безопасности для хранилищ сохраняемости в фабрике приложений Windows Server, в разделе [конфигурацию безопасности для хранилищ сохраняемости в фабрике приложений](http://go.microsoft.com/fwlink/?LinkId=201208)</span><span class="sxs-lookup"><span data-stu-id="db9a2-112"> security for persistence stores with Windows Server App Fabric, see [Security Configuration for Persistence Stores in App Fabric](http://go.microsoft.com/fwlink/?LinkId=201208)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="db9a2-113">Клиент, имеющий доступ к данным собственного экземпляра в хранилище экземпляров, также получает доступ и ко всем другим экземплярам в этом хранилище экземпляров.</span><span class="sxs-lookup"><span data-stu-id="db9a2-113">A client that has access to its own instance data in the instance store has access to all other instances in the same instance store.</span></span> <span data-ttu-id="db9a2-114">Хранилище экземпляров не поддерживает указание прав доступа на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="db9a2-114">The instance store does not support specifying security permissions at the instance level.</span></span> <span data-ttu-id="db9a2-115">Для обеспечения доступа к различным хранилищам экземпляров необходимо создать отдельные хранилища экземпляров и настроить доступ к ним различных групп и пользователей.</span><span class="sxs-lookup"><span data-stu-id="db9a2-115">You should create separate instance stores and map different groups/users to have access to different stores.</span></span>
