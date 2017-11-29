---
title: "Период обнаружения запускаемых экземпляров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a78f8404d5e6b9d63c9455d059dcbb9a76f8c18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="runnable-instances-detection-period"></a><span data-ttu-id="c80c6-102">Период обнаружения запускаемых экземпляров</span><span class="sxs-lookup"><span data-stu-id="c80c6-102">Runnable Instances Detection Period</span></span>
<span data-ttu-id="c80c6-103">Хранилище экземпляров рабочих процессов SQL выполняется в форме внутренней задачи, которая периодически активизируется и обнаруживает в базе данных сохраняемости экземпляры, которые могут быть запущены или активированы.</span><span class="sxs-lookup"><span data-stu-id="c80c6-103">The SQL Workflow Instance Store runs an internal task that periodically wakes up and detects runnable or activatable instances in the persistence database.</span></span> <span data-ttu-id="c80c6-104">**Период обнаружения запускаемых экземпляров** свойства хранилища экземпляров рабочих процессов SQL указывает период времени, после которого хранилище экземпляров рабочих процессов SQL выполняет задачу обнаружения выполняемых или активируемых рабочих процессов экземпляры в базе данных постоянного хранения после предыдущего цикла обнаружения.</span><span class="sxs-lookup"><span data-stu-id="c80c6-104">The **Runnable Instances Detection Period** property of the SQL Workflow Instance Store specifies the time period after which the SQL Workflow Instance Store runs a detection task to detect any runnable or activatable workflow instances in the persistence database after the previous detection cycle.</span></span>  
  
 <span data-ttu-id="c80c6-105">Установка более короткого интервала для этого свойства сокращает временной интервал между завершением отсчета таймера, связанного с экземпляром рабочего процесса, и оповещением о событии с последующей загрузкой экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c80c6-105">Setting a shorter interval for this property reduces the time between the expiration of a timer associated with a workflow instance and the signaling of the event and subsequent loading of the instance.</span></span> <span data-ttu-id="c80c6-106">Однако это также увеличивает нагрузку по обработке на узел и может быть нежелательным в ситуациях, в которых отказы постоянных таймеров и/или узлов случаются редко.</span><span class="sxs-lookup"><span data-stu-id="c80c6-106">However, it also increases the processing load on a host and may not be desirable in scenarios where durable timers and/or host failures are rare.</span></span> <span data-ttu-id="c80c6-107">Свойство имеет тип TimeSpan; значение свойства соответствует формату «чч:мм:сс».</span><span class="sxs-lookup"><span data-stu-id="c80c6-107">The type of the property is TimeSpan and the value of the property follows the format: hh:mm:ss.</span></span> <span data-ttu-id="c80c6-108">Минимальное значение данного свойства равно 00:00:01.</span><span class="sxs-lookup"><span data-stu-id="c80c6-108">The minimum value for this property is 00:00:01.</span></span> <span data-ttu-id="c80c6-109">Значение свойства по умолчанию равно 00:00:05.</span><span class="sxs-lookup"><span data-stu-id="c80c6-109">The default value for the property is 00:00:05.</span></span>  
  
 <span data-ttu-id="c80c6-110">Обнаружение и активация экземпляров рабочего процесса, запускаемого и активируемый Подробнее [активации экземпляра](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span><span class="sxs-lookup"><span data-stu-id="c80c6-110">For more information detecting and activating runnable and activatable workflow instances, see [Instance Activation](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span></span>
