---
title: Объект My.Settings (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: a962f7cce961b1ee6829702a6815ba02c534efb4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840371"
---
# <a name="mysettings-object"></a><span data-ttu-id="20ce5-102">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="20ce5-102">My.Settings Object</span></span>
<span data-ttu-id="20ce5-103">Предоставляет свойства и методы для доступа к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="20ce5-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20ce5-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="20ce5-104">Remarks</span></span>  
 <span data-ttu-id="20ce5-105">`My.Settings` Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="20ce5-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="20ce5-106">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="20ce5-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="20ce5-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="20ce5-107">Properties</span></span>  
 <span data-ttu-id="20ce5-108">Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="20ce5-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="20ce5-109">Чтобы добавить или удалить параметры, используйте **конструктор параметров**.</span><span class="sxs-lookup"><span data-stu-id="20ce5-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="20ce5-110">Каждый параметр имеет **имя**, **тип**, **область**, и **значение**, и эти параметры определяют, как свойство для доступа к каждому параметру отображается в `My.Settings` объекта:</span><span class="sxs-lookup"><span data-stu-id="20ce5-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="20ce5-111">**Имя** определяет имя свойства.</span><span class="sxs-lookup"><span data-stu-id="20ce5-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="20ce5-112">**Тип** определяет тип свойства.</span><span class="sxs-lookup"><span data-stu-id="20ce5-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="20ce5-113">**Область** указывает, является ли свойство только для чтения.</span><span class="sxs-lookup"><span data-stu-id="20ce5-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="20ce5-114">Если значение равно **приложения**, свойство только для чтения; если значение равно **пользователя**, свойства чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="20ce5-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="20ce5-115">**Значение** значение свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="20ce5-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20ce5-116">Методы</span><span class="sxs-lookup"><span data-stu-id="20ce5-116">Methods</span></span>  
  
|<span data-ttu-id="20ce5-117">Метод</span><span class="sxs-lookup"><span data-stu-id="20ce5-117">Method</span></span>|<span data-ttu-id="20ce5-118">Описание</span><span class="sxs-lookup"><span data-stu-id="20ce5-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="20ce5-119">Перезагружает параметры пользователя из последними сохраненными значениями.</span><span class="sxs-lookup"><span data-stu-id="20ce5-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="20ce5-120">Сохраняет текущие параметры пользователя.</span><span class="sxs-lookup"><span data-stu-id="20ce5-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="20ce5-121">`My.Settings` Также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.</span><span class="sxs-lookup"><span data-stu-id="20ce5-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="20ce5-122">Задачи</span><span class="sxs-lookup"><span data-stu-id="20ce5-122">Tasks</span></span>  
 <span data-ttu-id="20ce5-123">В следующей таблице перечислены примеры задач, связанных с `My.Settings` объекта.</span><span class="sxs-lookup"><span data-stu-id="20ce5-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="20ce5-124">Кому</span><span class="sxs-lookup"><span data-stu-id="20ce5-124">To</span></span>|<span data-ttu-id="20ce5-125">См.</span><span class="sxs-lookup"><span data-stu-id="20ce5-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="20ce5-126">Чтение параметров приложения</span><span class="sxs-lookup"><span data-stu-id="20ce5-126">Read an application setting</span></span>|[<span data-ttu-id="20ce5-127">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="20ce5-128">Изменение параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="20ce5-128">Change a user setting</span></span>|[<span data-ttu-id="20ce5-129">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="20ce5-130">Сохранение пользовательских параметров</span><span class="sxs-lookup"><span data-stu-id="20ce5-130">Persist user settings</span></span>|[<span data-ttu-id="20ce5-131">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="20ce5-132">Создать таблицу свойств для пользовательских параметров</span><span class="sxs-lookup"><span data-stu-id="20ce5-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="20ce5-133">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="20ce5-134">Пример</span><span class="sxs-lookup"><span data-stu-id="20ce5-134">Example</span></span>  
 <span data-ttu-id="20ce5-135">В этом пример выводится значение параметра `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="20ce5-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="20ce5-136">Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="20ce5-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ce5-137">См. также</span><span class="sxs-lookup"><span data-stu-id="20ce5-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="20ce5-138">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="20ce5-139">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="20ce5-140">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="20ce5-141">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20ce5-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="20ce5-142">Управление параметрами приложения (.NET)</span><span class="sxs-lookup"><span data-stu-id="20ce5-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
