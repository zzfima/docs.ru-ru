---
title: Действие завершения экземпляра
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 646015fbcdb7c734ae8584c7ca3979d64b81339f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513205"
---
# <a name="instance-completion-action"></a><span data-ttu-id="01af0-102">Действие завершения экземпляра</span><span class="sxs-lookup"><span data-stu-id="01af0-102">Instance Completion Action</span></span>
<span data-ttu-id="01af0-103">**Действие завершения экземпляра** хранилища экземпляров рабочих процессов SQL позволяет задать данные и метаданные экземпляров рабочих процессов удаляется из базы данных сохраняемости после завершения работы экземпляров.</span><span class="sxs-lookup"><span data-stu-id="01af0-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="01af0-104">Допустимые значения для этого свойства **DeleteAll** и **DeleteNothing**.</span><span class="sxs-lookup"><span data-stu-id="01af0-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="01af0-105">Эти варианты описаны в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="01af0-105">The following list describes these options:</span></span>  
  
-   <span data-ttu-id="01af0-106">**DeleteAll (по умолчанию).**</span><span class="sxs-lookup"><span data-stu-id="01af0-106">**DeleteAll (default).**</span></span> <span data-ttu-id="01af0-107">Если свойство имеет значение DeleteAll, данные и метаданные экземпляров рабочих процессов удаляются из базы данных сохраняемости после завершения работы экземпляров.</span><span class="sxs-lookup"><span data-stu-id="01af0-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
-   <span data-ttu-id="01af0-108">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="01af0-108">**DeleteNothing.**</span></span> <span data-ttu-id="01af0-109">Если свойство имеет значение DeleteNothing, данные и метаданные экземпляров рабочих процессов не удаляются из базы данных постоянного сохранения даже после завершения работы экземпляров.</span><span class="sxs-lookup"><span data-stu-id="01af0-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="01af0-110">Если данные о состоянии экземпляров сохраняются после завершения работы, размер базы данных сохраняемости начинает увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="01af0-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="01af0-111">По мере роста базы данных операции, выполняемые подсистемой сохраняемости, занимают все больше времени, поэтому рекомендуется периодически удалять сведения о состоянии экземпляров из базы данных сохраняемости, чтобы службы работали с удовлетворительной производительностью.</span><span class="sxs-lookup"><span data-stu-id="01af0-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>
