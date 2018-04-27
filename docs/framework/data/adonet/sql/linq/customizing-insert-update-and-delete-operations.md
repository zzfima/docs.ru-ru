---
title: Настройка операций вставки, обновления и удаления
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07eef055-8f6c-414d-850e-d323ff946cd0
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 410385d1689a9fd15a1399411f601e407d590830
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-insert-update-and-delete-operations"></a><span data-ttu-id="2da37-102">Настройка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="2da37-102">Customizing Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="2da37-103">По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает динамический SQL для выполнения операций чтения, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="2da37-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL to implement insert, read, update, and delete operations.</span></span> <span data-ttu-id="2da37-104">Однако на практике обычно приходится настраивать приложение в соответствии с собственными бизнес-требованиями.</span><span class="sxs-lookup"><span data-stu-id="2da37-104">In practice, however, you typically customize your application to suit your business needs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2da37-105">Если вы используете Visual Studio, можно использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для настройки вставки, обновления и удаления действия.</span><span class="sxs-lookup"><span data-stu-id="2da37-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to customize insert, update, and delete actions.</span></span>  
  
 <span data-ttu-id="2da37-106">В данном разделе описываются методы, представляемые [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="2da37-106">This section of topics describes the techniques that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations in your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2da37-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2da37-107">In This Section</span></span>  
 [<span data-ttu-id="2da37-108">Настройка операций. Общие сведения</span><span class="sxs-lookup"><span data-stu-id="2da37-108">Customizing Operations: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-overview.md)  
 <span data-ttu-id="2da37-109">Содержит описание различных методов, представленных в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], для настройки операций вставки, чтения, обновления и удаления в приложении.</span><span class="sxs-lookup"><span data-stu-id="2da37-109">Describes the various techniques [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides for customizing insert, read, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="2da37-110">Операции вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="2da37-110">Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)  
 <span data-ttu-id="2da37-111">Содержит описание заданных по умолчанию процессов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] по управлению данными базы данных.</span><span class="sxs-lookup"><span data-stu-id="2da37-111">Describes the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default processes for manipulating database data.</span></span>  
  
 [<span data-ttu-id="2da37-112">Ответственность разработчика при переопределении поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2da37-112">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)  
 <span data-ttu-id="2da37-113">Содержит описание роли разработчиков в реализации требований, не примененных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2da37-113">Describes the role of the developer in implementing requirements not enforced by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="2da37-114">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="2da37-114">Adding Business Logic By Using Partial Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)  
 <span data-ttu-id="2da37-115">Содержит описание использования разделяемых методов для переопределения автоматически сгенерированных методов.</span><span class="sxs-lookup"><span data-stu-id="2da37-115">Describes how to use partial methods to override autogenerated methods.</span></span>
