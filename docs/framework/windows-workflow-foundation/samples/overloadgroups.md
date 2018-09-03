---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 0773e76d36b25ad5485cc8912c7012815412de9f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43469873"
---
# <a name="overloadgroups"></a><span data-ttu-id="3a275-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="3a275-102">OverloadGroups</span></span>
<span data-ttu-id="3a275-103">Этот образец состоит из действия (`CreateLocation`) с двумя интересными характеристиками.</span><span class="sxs-lookup"><span data-stu-id="3a275-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="3a275-104">Оно имеет несколько обязательных и несколько необязательных аргументов.</span><span class="sxs-lookup"><span data-stu-id="3a275-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="3a275-105">С его помощью пользователь может выбрать предоставление одного или двух разных наборов аргументов.</span><span class="sxs-lookup"><span data-stu-id="3a275-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="3a275-106">Такие поведения достигаются с помощью двух следующих функций.</span><span class="sxs-lookup"><span data-stu-id="3a275-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="3a275-107">`[isRequired]` проверяет, является ли свойство или определенное действие assign, и, если не является, формирует исключение.</span><span class="sxs-lookup"><span data-stu-id="3a275-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="3a275-108">`[OverloadGroup]` составляет набор аргументов, чтобы пользователь действия мог выбрать, какой из наборов будет использован.</span><span class="sxs-lookup"><span data-stu-id="3a275-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="3a275-109">В одном и том же экземпляре пользователь не может использовать аргументы из различных групп перегруженных вариантов.</span><span class="sxs-lookup"><span data-stu-id="3a275-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="3a275-110">После настройки различных рабочих процессов вызовите метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.Constraint>.</span><span class="sxs-lookup"><span data-stu-id="3a275-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="3a275-111">Вывести объекты <xref:System.Activities.Validation.Constraint> в консоль.</span><span class="sxs-lookup"><span data-stu-id="3a275-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3a275-112">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3a275-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3a275-113">Откройте **OverloadGroups.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a275-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3a275-114">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="3a275-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3a275-115">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3a275-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3a275-116">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3a275-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3a275-117">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="3a275-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3a275-118">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3a275-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
