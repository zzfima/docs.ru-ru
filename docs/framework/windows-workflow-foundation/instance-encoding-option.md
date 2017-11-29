---
title: "Параметр кодировки экземпляров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5803b034eeecac66aa20951c5167b9e666f1fa8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="instance-encoding-option"></a><span data-ttu-id="52799-102">Параметр кодировки экземпляров</span><span class="sxs-lookup"><span data-stu-id="52799-102">Instance Encoding Option</span></span>
<span data-ttu-id="52799-103">**Instance Encoding Option** свойство хранилища экземпляров рабочих процессов SQL позволяет указать, должен ли поставщик сохраняемости SQL сжимать сведения о состоянии экземпляра рабочего процесса с применением алгоритма GZip перед сохранением сведения в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="52799-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="52799-104">Допустимы значения этого свойства GZip и None.</span><span class="sxs-lookup"><span data-stu-id="52799-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="52799-105">По умолчанию используется значение None.</span><span class="sxs-lookup"><span data-stu-id="52799-105">The default value is None.</span></span> <span data-ttu-id="52799-106">Эти варианты описаны в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="52799-106">The following list describes these options.</span></span>  
  
1.  <span data-ttu-id="52799-107">**GZip**.</span><span class="sxs-lookup"><span data-stu-id="52799-107">**GZip**.</span></span> <span data-ttu-id="52799-108">Поставщик сохраняемости кодирует сведения о состоянии с использованием алгоритма сжатия GZip перед их сохранением в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="52799-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2.  <span data-ttu-id="52799-109">**Нет**.</span><span class="sxs-lookup"><span data-stu-id="52799-109">**None**.</span></span> <span data-ttu-id="52799-110">Поставщик сохраняемости не сжимает сведения о состоянии перед их сохранением в базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="52799-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="52799-111">При кодировании и сжатии сведений о состоянии экземпляра рабочего процесса с использованием экземпляра GZip снижается потребление памяти базой данных SQL, а также снижается нагрузка на сеть (в случае если база данных расположена на другом компьютере в сети, а не на компьютере, на котором запущена служба рабочего процесса).</span><span class="sxs-lookup"><span data-stu-id="52799-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="52799-112">Общие рекомендации заключается в задании **Instance Encoding Option** свойства **нет** при небольших состояние экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="52799-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>
