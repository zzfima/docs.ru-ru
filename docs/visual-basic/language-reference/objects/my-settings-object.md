---
title: Объект My.Settings (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 5d6d56e4a1eddcb687fe042568509ba489aa8bb3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973474"
---
# <a name="mysettings-object"></a><span data-ttu-id="e7b9e-102">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="e7b9e-102">My.Settings Object</span></span>
<span data-ttu-id="e7b9e-103">Предоставляет свойства и методы для доступа к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7b9e-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7b9e-104">Remarks</span></span>  
 <span data-ttu-id="e7b9e-105">`My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="e7b9e-106">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e7b9e-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e7b9e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e7b9e-107">Properties</span></span>  
 <span data-ttu-id="e7b9e-108">Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="e7b9e-109">Чтобы добавить или удалить параметры, используйте **конструктор параметров**.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="e7b9e-110">Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как свойство для доступа к каждому параметру отображается в `My.Settings` объекта:</span><span class="sxs-lookup"><span data-stu-id="e7b9e-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="e7b9e-111">**Имя** определяет имя свойства.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="e7b9e-112">**Тип** определяет тип свойства.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="e7b9e-113">**Область** указывает, является ли свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="e7b9e-114">Если значение равно **приложения**, свойство только для чтения; если значение равно **пользователя**, свойства чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="e7b9e-115">**Значение** значение свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7b9e-116">Методы</span><span class="sxs-lookup"><span data-stu-id="e7b9e-116">Methods</span></span>  
  
|<span data-ttu-id="e7b9e-117">Метод</span><span class="sxs-lookup"><span data-stu-id="e7b9e-117">Method</span></span>|<span data-ttu-id="e7b9e-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="e7b9e-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="e7b9e-119">Перезагружает параметры пользователя из последними сохраненными значениями.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="e7b9e-120">Сохраняет текущие параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="e7b9e-121">`My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="e7b9e-122">Задачи</span><span class="sxs-lookup"><span data-stu-id="e7b9e-122">Tasks</span></span>  
 <span data-ttu-id="e7b9e-123">В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="e7b9e-124">Кому</span><span class="sxs-lookup"><span data-stu-id="e7b9e-124">To</span></span>|<span data-ttu-id="e7b9e-125">См.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="e7b9e-126">Чтение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="e7b9e-126">Read an application setting</span></span>|[<span data-ttu-id="e7b9e-127">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="e7b9e-128">Изменение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="e7b9e-128">Change a user setting</span></span>|[<span data-ttu-id="e7b9e-129">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="e7b9e-130">Сохранение пользовательских параметров</span><span class="sxs-lookup"><span data-stu-id="e7b9e-130">Persist user settings</span></span>|[<span data-ttu-id="e7b9e-131">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="e7b9e-132">Создать таблицу свойств для пользовательских параметров</span><span class="sxs-lookup"><span data-stu-id="e7b9e-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="e7b9e-133">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="e7b9e-134">Пример</span><span class="sxs-lookup"><span data-stu-id="e7b9e-134">Example</span></span>  
 <span data-ttu-id="e7b9e-135">В этом пример выводится значение параметра `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="e7b9e-136">Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="e7b9e-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b9e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e7b9e-137">See also</span></span>
- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="e7b9e-138">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="e7b9e-139">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="e7b9e-140">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="e7b9e-141">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7b9e-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="e7b9e-142">Управление параметрами приложения (.NET)</span><span class="sxs-lookup"><span data-stu-id="e7b9e-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
