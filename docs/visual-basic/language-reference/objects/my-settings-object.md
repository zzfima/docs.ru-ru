---
title: "Объект My.Settings | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4d6ee6d2d54c0e3a4af3b7cdec5f81166ce3ddce
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="mysettings-object"></a><span data-ttu-id="913ba-102">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="913ba-102">My.Settings Object</span></span>
<span data-ttu-id="913ba-103">Предоставляет свойства и методы для доступа к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="913ba-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="913ba-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="913ba-104">Remarks</span></span>  
 <span data-ttu-id="913ba-105">`My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для приложения.</span><span class="sxs-lookup"><span data-stu-id="913ba-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="913ba-106">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="913ba-106">For more information, see [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="913ba-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="913ba-107">Properties</span></span>  
 <span data-ttu-id="913ba-108">Свойства `My.Settings` обеспечивают доступ к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="913ba-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="913ba-109">Чтобы добавить или удалить параметры, используйте **конструктор параметров**.</span><span class="sxs-lookup"><span data-stu-id="913ba-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="913ba-110">Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как отображается свойство для доступа к каждому параметру в `My.Settings` объекта:</span><span class="sxs-lookup"><span data-stu-id="913ba-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="913ba-111">**Имя** определяет имя свойства.</span><span class="sxs-lookup"><span data-stu-id="913ba-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="913ba-112">**Тип** определяет тип свойства.</span><span class="sxs-lookup"><span data-stu-id="913ba-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="913ba-113">**Область** указывает, является ли свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="913ba-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="913ba-114">Если значение равно **приложения**, свойство доступно только для чтения; если значение **пользователя**, свойства чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="913ba-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="913ba-115">**Значение** значение свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="913ba-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="913ba-116">Методы</span><span class="sxs-lookup"><span data-stu-id="913ba-116">Methods</span></span>  
  
|<span data-ttu-id="913ba-117">Метод</span><span class="sxs-lookup"><span data-stu-id="913ba-117">Method</span></span>|<span data-ttu-id="913ba-118">Описание</span><span class="sxs-lookup"><span data-stu-id="913ba-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="913ba-119">Перезагружает параметры пользователя из последних сохраненных значений.</span><span class="sxs-lookup"><span data-stu-id="913ba-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="913ba-120">Сохраняет текущие параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="913ba-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="913ba-121">`My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase>класса.</xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="913ba-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="913ba-122">Задачи</span><span class="sxs-lookup"><span data-stu-id="913ba-122">Tasks</span></span>  
 <span data-ttu-id="913ba-123">В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.</span><span class="sxs-lookup"><span data-stu-id="913ba-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="913ba-124">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="913ba-124">To</span></span>|<span data-ttu-id="913ba-125">См.</span><span class="sxs-lookup"><span data-stu-id="913ba-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="913ba-126">Чтение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="913ba-126">Read an application setting</span></span>|[<span data-ttu-id="913ba-127">Практическое руководство: чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="913ba-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="913ba-128">Изменение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="913ba-128">Change a user setting</span></span>|[<span data-ttu-id="913ba-129">Практическое руководство: изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="913ba-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="913ba-130">Сохранение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="913ba-130">Persist user settings</span></span>|[<span data-ttu-id="913ba-131">Практическое руководство: сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="913ba-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="913ba-132">Создание сетки свойств для параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="913ba-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="913ba-133">Практическое руководство: создание сетки свойств для параметров пользователя в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="913ba-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="913ba-134">Пример</span><span class="sxs-lookup"><span data-stu-id="913ba-134">Example</span></span>  
 <span data-ttu-id="913ba-135">В этом примере отображается значение `Nickname` параметр.</span><span class="sxs-lookup"><span data-stu-id="913ba-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 <span data-ttu-id="913ba-136">[!code-vb[VbVbalrMyResources&#14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="913ba-136">[!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span></span>  
  
 <span data-ttu-id="913ba-137">Для работы этого примера приложение должно иметь `Nickname` параметр типа `String`.</span><span class="sxs-lookup"><span data-stu-id="913ba-137">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913ba-138">См. также</span><span class="sxs-lookup"><span data-stu-id="913ba-138">See Also</span></span>  
 <span data-ttu-id="913ba-139"><xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="913ba-139"><xref:System.Configuration.ApplicationSettingsBase></span></span>   
<span data-ttu-id="913ba-140"> [Практическое руководство: чтение параметров приложения в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="913ba-140"> [How to: Read Application Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
<span data-ttu-id="913ba-141"> [Практическое руководство: изменение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="913ba-141"> [How to: Change User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
<span data-ttu-id="913ba-142"> [Практическое руководство: сохранение пользовательских параметров в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="913ba-142"> [How to: Persist User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
<span data-ttu-id="913ba-143"> [Практическое руководство: создание сетки свойств для параметров пользователя в Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="913ba-143"> [How to: Create Property Grids for User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
<span data-ttu-id="913ba-144"> [Управление параметрами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span><span class="sxs-lookup"><span data-stu-id="913ba-144"> [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span></span>
