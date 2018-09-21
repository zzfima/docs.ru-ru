---
title: Отслеживание переменной и аргумента
ms.date: 03/30/2017
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
ms.openlocfilehash: 45ed3761cd7ead82650023b93a2f32a43e847339
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46538051"
---
# <a name="variable-and-argument-tracking"></a><span data-ttu-id="29a51-102">Отслеживание переменной и аргумента</span><span class="sxs-lookup"><span data-stu-id="29a51-102">Variable and Argument Tracking</span></span>
<span data-ttu-id="29a51-103">При отслеживании выполнения рабочего процесса часто бывает полезно извлекать данные.</span><span class="sxs-lookup"><span data-stu-id="29a51-103">When tracking the execution of a workflow, it is often useful to extract data.</span></span> <span data-ttu-id="29a51-104">Это обеспечивает дополнительный контекст при доступе к последующему выполнению записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="29a51-104">This provides additional context when accessing a tracking record post execution.</span></span> <span data-ttu-id="29a51-105">В [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] можно извлекать любую видимую переменную или аргумент, находящиеся в рамках области любого действия в рабочем процессе, при помощи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="29a51-105">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], you can extract any visible variable or argument within the scope of any activity in a workflow using tracking.</span></span> <span data-ttu-id="29a51-106">Профили отслеживания упрощают извлечение данных.</span><span class="sxs-lookup"><span data-stu-id="29a51-106">Tracking profiles make it easy to extract data.</span></span>  
  
## <a name="variables-and-arguments"></a><span data-ttu-id="29a51-107">Переменные и аргументы</span><span class="sxs-lookup"><span data-stu-id="29a51-107">Variables and Arguments</span></span>  
 <span data-ttu-id="29a51-108">Переменные и аргументы извлекаются при создании действием записи ActivityStateRecord.</span><span class="sxs-lookup"><span data-stu-id="29a51-108">Variables and arguments are extracted when an activity emits an ActivityStateRecord.</span></span>  <span data-ttu-id="29a51-109">Переменная доступна для извлечения, только если она записана в области этого действия.</span><span class="sxs-lookup"><span data-stu-id="29a51-109">A variable is available for extraction only if it is within the scope of the activity.</span></span> <span data-ttu-id="29a51-110">Переменная, извлекаемая в действии, задается следующим образом.</span><span class="sxs-lookup"><span data-stu-id="29a51-110">A variable to be extracted within an activity is specified in the following manner:</span></span>  
  
-   <span data-ttu-id="29a51-111">Если переменная задана именем переменной, отслеживание будет искать переменную в текущем отслеживаемом действии и в родительских действиях.</span><span class="sxs-lookup"><span data-stu-id="29a51-111">If a variable is specified by the variable name, then tracking looks for the variable within the current activity being tracked and in parent activities.</span></span> <span data-ttu-id="29a51-112">Будет выполнен поиск переменной в области текущего действия и в родительской области.</span><span class="sxs-lookup"><span data-stu-id="29a51-112">The variable is searched in current activity scope and in parent scope.</span></span>  
  
-   <span data-ttu-id="29a51-113">Если извлекаемые переменные заданы с помощью имени = "\*», а затем извлекаются все переменные внутри текущего отслеживаемого действия.</span><span class="sxs-lookup"><span data-stu-id="29a51-113">If variables to be extracted are specified by using name="\*", then all variables within the current activity being tracked are extracted.</span></span> <span data-ttu-id="29a51-114">В этом случае переменные, находящиеся в области, но не определенные в родительских действиях, извлечены не будут.</span><span class="sxs-lookup"><span data-stu-id="29a51-114">In this case variables that are in scope but defined in parent activities are not extracted.</span></span>  
  
 <span data-ttu-id="29a51-115">При извлечении аргументов извлекаемые аргументы зависят от состояния действия.</span><span class="sxs-lookup"><span data-stu-id="29a51-115">When extracting arguments, the arguments extracted depend on the state of the activity.</span></span> <span data-ttu-id="29a51-116">Если состояние действия - «Выполнение», тогда только `InArguments` будут доступны для извлечения.</span><span class="sxs-lookup"><span data-stu-id="29a51-116">When the state of an activity is Executing, then only the `InArguments` are available for extraction.</span></span> <span data-ttu-id="29a51-117">Для любого другого состояния действия («Закрыто», «Ошибка», «Отменено») оба аргумента, InArguments и OutArguments, доступны для извлечения.</span><span class="sxs-lookup"><span data-stu-id="29a51-117">For any other activity state (Closed, Faulted, Canceled), all arguments, both InArguments and OutArguments, are available for extraction.</span></span>  
  
 <span data-ttu-id="29a51-118">В следующем примере показан запрос состояния действия, который извлекает переменные и аргументы при создании записи отслеживания действия `Closed`.</span><span class="sxs-lookup"><span data-stu-id="29a51-118">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="29a51-119">Переменные и аргументы могут быть извлечены при помощи <xref:System.Activities.Tracking.ActivityStateRecord>, поэтому подписка на них выполняется в рамках профиля отслеживания с использованием запроса <xref:System.Activities.Tracking.ActivityStateQuery>.</span><span class="sxs-lookup"><span data-stu-id="29a51-119">Variables and arguments can be extracted only with an <xref:System.Activities.Tracking.ActivityStateRecord> and thus are subscribed to within a tracking profile using <xref:System.Activities.Tracking.ActivityStateQuery>.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a><span data-ttu-id="29a51-120">Защита информации, сохраняемой в переменных и аргументах</span><span class="sxs-lookup"><span data-stu-id="29a51-120">Protecting Information Stored Within Variables and Arguments</span></span>  
 <span data-ttu-id="29a51-121">Отслеживаемая переменная или аргумент по умолчанию становятся видимыми в среде выполнения WF.</span><span class="sxs-lookup"><span data-stu-id="29a51-121">A tracked variable or argument is by default made visible by the WF runtime.</span></span> <span data-ttu-id="29a51-122">Разработчик рабочих процессов может установить защиту против доступа, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="29a51-122">A workflow developer can protect it from being accessed by taking the following steps:</span></span>  
  
1.  <span data-ttu-id="29a51-123">Зашифруйте значение переменной.</span><span class="sxs-lookup"><span data-stu-id="29a51-123">Encrypt the value of a variable.</span></span>  
  
2.  <span data-ttu-id="29a51-124">Контролируйте создание профиля отслеживания для предотвращения извлечения переменной или аргумента.</span><span class="sxs-lookup"><span data-stu-id="29a51-124">Control the authoring of a tracking profile to prevent the extraction of a variable or argument.</span></span>  
  
3.  <span data-ttu-id="29a51-125">Для пользовательских участников отслеживания убедитесь, что код WF не раскрывает конфиденциальные сведения, сохраняемую в переменных и аргументах.</span><span class="sxs-lookup"><span data-stu-id="29a51-125">For custom tracking participants ensure that the WF code does not disclose sensitive information that is stored in variables or arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a51-126">См. также</span><span class="sxs-lookup"><span data-stu-id="29a51-126">See Also</span></span>  
 [<span data-ttu-id="29a51-127">Мониторинг Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="29a51-127">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="29a51-128">Мониторинг приложений с помощью фабрики приложения</span><span class="sxs-lookup"><span data-stu-id="29a51-128">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
