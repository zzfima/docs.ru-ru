---
title: Объект My.Settings
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 54176ae6706311b17227c7dc21a5060c9b369753
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mysettings-object"></a><span data-ttu-id="1e75f-102">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="1e75f-102">My.Settings Object</span></span>
<span data-ttu-id="1e75f-103">Предоставляет свойства и методы для доступа к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="1e75f-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e75f-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e75f-104">Remarks</span></span>  
 <span data-ttu-id="1e75f-105">`My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="1e75f-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="1e75f-106">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="1e75f-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1e75f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="1e75f-107">Properties</span></span>  
 <span data-ttu-id="1e75f-108">Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="1e75f-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="1e75f-109">Чтобы добавить или удалить параметры, используйте **конструктор параметров**.</span><span class="sxs-lookup"><span data-stu-id="1e75f-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="1e75f-110">Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как свойство, доступ к каждому параметру отображается в `My.Settings` объекта:</span><span class="sxs-lookup"><span data-stu-id="1e75f-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="1e75f-111">**Имя** определяет имя свойства.</span><span class="sxs-lookup"><span data-stu-id="1e75f-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="1e75f-112">**Тип** определяет тип свойства.</span><span class="sxs-lookup"><span data-stu-id="1e75f-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="1e75f-113">**Область** указывает, является ли свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1e75f-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="1e75f-114">Если значение равно **приложения**, свойство доступно только для чтения; если значение равно **пользователя**, свойство доступно для чтения записи.</span><span class="sxs-lookup"><span data-stu-id="1e75f-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="1e75f-115">**Значение** значение свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1e75f-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e75f-116">Методы</span><span class="sxs-lookup"><span data-stu-id="1e75f-116">Methods</span></span>  
  
|<span data-ttu-id="1e75f-117">Метод</span><span class="sxs-lookup"><span data-stu-id="1e75f-117">Method</span></span>|<span data-ttu-id="1e75f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1e75f-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="1e75f-119">Перезагружает параметры пользователя из последними сохраненными значениями.</span><span class="sxs-lookup"><span data-stu-id="1e75f-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="1e75f-120">Сохраняет текущие параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="1e75f-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="1e75f-121">`My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.</span><span class="sxs-lookup"><span data-stu-id="1e75f-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="1e75f-122">Задачи</span><span class="sxs-lookup"><span data-stu-id="1e75f-122">Tasks</span></span>  
 <span data-ttu-id="1e75f-123">В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.</span><span class="sxs-lookup"><span data-stu-id="1e75f-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="1e75f-124">Кому</span><span class="sxs-lookup"><span data-stu-id="1e75f-124">To</span></span>|<span data-ttu-id="1e75f-125">См.</span><span class="sxs-lookup"><span data-stu-id="1e75f-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="1e75f-126">Чтение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="1e75f-126">Read an application setting</span></span>|[<span data-ttu-id="1e75f-127">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="1e75f-128">Изменение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="1e75f-128">Change a user setting</span></span>|[<span data-ttu-id="1e75f-129">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="1e75f-130">Сохранение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="1e75f-130">Persist user settings</span></span>|[<span data-ttu-id="1e75f-131">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="1e75f-132">Создание сетки свойств для параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="1e75f-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="1e75f-133">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="1e75f-134">Пример</span><span class="sxs-lookup"><span data-stu-id="1e75f-134">Example</span></span>  
 <span data-ttu-id="1e75f-135">В этом пример выводится значение параметра `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="1e75f-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 <span data-ttu-id="1e75f-136">Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="1e75f-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e75f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="1e75f-137">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [<span data-ttu-id="1e75f-138">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="1e75f-139">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="1e75f-140">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="1e75f-141">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e75f-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="1e75f-142">Управление параметрами приложения (.NET)</span><span class="sxs-lookup"><span data-stu-id="1e75f-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
