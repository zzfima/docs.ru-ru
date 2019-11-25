---
title: Объект My.Settings
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350355"
---
# <a name="mysettings-object"></a><span data-ttu-id="bdfb8-102">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="bdfb8-102">My.Settings Object</span></span>
<span data-ttu-id="bdfb8-103">Provides properties and methods for accessing the application's settings.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdfb8-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="bdfb8-104">Remarks</span></span>  
 <span data-ttu-id="bdfb8-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="bdfb8-106">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="bdfb8-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bdfb8-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="bdfb8-107">Properties</span></span>  
 <span data-ttu-id="bdfb8-108">Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="bdfb8-109">To add or remove settings, use the **Settings Designer**.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="bdfb8-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span><span class="sxs-lookup"><span data-stu-id="bdfb8-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="bdfb8-111">**Name** determines the name of the property.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="bdfb8-112">**Type** determines the type of the property.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="bdfb8-113">**Scope** indicates if the property is read-only.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="bdfb8-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="bdfb8-115">**Value** is the default value of the property.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bdfb8-116">Методы</span><span class="sxs-lookup"><span data-stu-id="bdfb8-116">Methods</span></span>  
  
|<span data-ttu-id="bdfb8-117">Метод</span><span class="sxs-lookup"><span data-stu-id="bdfb8-117">Method</span></span>|<span data-ttu-id="bdfb8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="bdfb8-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="bdfb8-119">Reloads the user settings from the last saved values.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="bdfb8-120">Saves the current user settings.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="bdfb8-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="bdfb8-122">Задачи</span><span class="sxs-lookup"><span data-stu-id="bdfb8-122">Tasks</span></span>  
 <span data-ttu-id="bdfb8-123">The following table lists examples of tasks involving the `My.Settings` object.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="bdfb8-124">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="bdfb8-124">To</span></span>|<span data-ttu-id="bdfb8-125">См.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="bdfb8-126">Read an application setting</span><span class="sxs-lookup"><span data-stu-id="bdfb8-126">Read an application setting</span></span>|[<span data-ttu-id="bdfb8-127">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="bdfb8-128">Change a user setting</span><span class="sxs-lookup"><span data-stu-id="bdfb8-128">Change a user setting</span></span>|[<span data-ttu-id="bdfb8-129">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="bdfb8-130">Persist user settings</span><span class="sxs-lookup"><span data-stu-id="bdfb8-130">Persist user settings</span></span>|[<span data-ttu-id="bdfb8-131">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="bdfb8-132">Create a property grid for user settings</span><span class="sxs-lookup"><span data-stu-id="bdfb8-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="bdfb8-133">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="bdfb8-134">Пример</span><span class="sxs-lookup"><span data-stu-id="bdfb8-134">Example</span></span>  
 <span data-ttu-id="bdfb8-135">В этом пример выводится значение параметра `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="bdfb8-136">Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="bdfb8-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfb8-137">См. также</span><span class="sxs-lookup"><span data-stu-id="bdfb8-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="bdfb8-138">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="bdfb8-139">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="bdfb8-140">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="bdfb8-141">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdfb8-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="bdfb8-142">Управление параметрами приложения (.NET)</span><span class="sxs-lookup"><span data-stu-id="bdfb8-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
