---
title: "Объект My.Settings"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords: My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f744460f8ea6c6c7f5c8c5e1658bd357e910def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mysettings-object"></a><span data-ttu-id="a8fbe-102">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="a8fbe-102">My.Settings Object</span></span>
<span data-ttu-id="a8fbe-103">Предоставляет свойства и методы для доступа к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8fbe-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8fbe-104">Remarks</span></span>  
 <span data-ttu-id="a8fbe-105">`My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="a8fbe-106">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a8fbe-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a8fbe-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="a8fbe-107">Properties</span></span>  
 <span data-ttu-id="a8fbe-108">Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="a8fbe-109">Чтобы добавить или удалить параметры, используйте **конструктор параметров**.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="a8fbe-110">Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как свойство, доступ к каждому параметру отображается в `My.Settings` объекта:</span><span class="sxs-lookup"><span data-stu-id="a8fbe-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="a8fbe-111">**Имя** определяет имя свойства.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="a8fbe-112">**Тип** определяет тип свойства.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="a8fbe-113">**Область** указывает, является ли свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="a8fbe-114">Если значение равно **приложения**, свойство доступно только для чтения; если значение равно **пользователя**, свойство доступно для чтения записи.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="a8fbe-115">**Значение** значение свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8fbe-116">Методы</span><span class="sxs-lookup"><span data-stu-id="a8fbe-116">Methods</span></span>  
  
|<span data-ttu-id="a8fbe-117">Метод</span><span class="sxs-lookup"><span data-stu-id="a8fbe-117">Method</span></span>|<span data-ttu-id="a8fbe-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a8fbe-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="a8fbe-119">Перезагружает параметры пользователя из последними сохраненными значениями.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="a8fbe-120">Сохраняет текущие параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="a8fbe-121">`My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="a8fbe-122">Задачи</span><span class="sxs-lookup"><span data-stu-id="a8fbe-122">Tasks</span></span>  
 <span data-ttu-id="a8fbe-123">В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="a8fbe-124">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="a8fbe-124">To</span></span>|<span data-ttu-id="a8fbe-125">См.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="a8fbe-126">Чтение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="a8fbe-126">Read an application setting</span></span>|[<span data-ttu-id="a8fbe-127">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="a8fbe-128">Изменение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="a8fbe-128">Change a user setting</span></span>|[<span data-ttu-id="a8fbe-129">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="a8fbe-130">Сохранение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="a8fbe-130">Persist user settings</span></span>|[<span data-ttu-id="a8fbe-131">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="a8fbe-132">Создание сетки свойств для параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="a8fbe-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="a8fbe-133">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="a8fbe-134">Пример</span><span class="sxs-lookup"><span data-stu-id="a8fbe-134">Example</span></span>  
 <span data-ttu-id="a8fbe-135">В этом пример выводится значение параметра `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 <span data-ttu-id="a8fbe-136">Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="a8fbe-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8fbe-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a8fbe-137">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [<span data-ttu-id="a8fbe-138">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="a8fbe-139">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="a8fbe-140">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="a8fbe-141">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8fbe-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="a8fbe-142">Управление параметрами приложения (.NET)</span><span class="sxs-lookup"><span data-stu-id="a8fbe-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
