---
title: Практическое руководство. Сохранение пользовательских параметров
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: b1026e400015ff7807144dca8e9ce6d72fe3d18e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74329632"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="a51fd-102">Практическое руководство. Сохранение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a51fd-102">How to: Persist User Settings in Visual Basic</span></span>

<span data-ttu-id="a51fd-103">Для сохранения изменений в параметрах пользователя можно использовать метод `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="a51fd-103">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="a51fd-104">Как правило, сохранение изменений в параметрах пользователя выполняется при завершении работы приложения.</span><span class="sxs-lookup"><span data-stu-id="a51fd-104">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="a51fd-105">Это связано с тем, что сохранение параметров может занять, в зависимости от разных факторов, несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="a51fd-105">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="a51fd-106">Дополнительные сведения см. в разделе [Объект My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="a51fd-106">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a51fd-107">Значения параметров с областью пользователя можно изменять и сохранять во время выполнения, однако параметры с областью приложения доступны только для чтения и не могут быть изменены программным способом.</span><span class="sxs-lookup"><span data-stu-id="a51fd-107">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="a51fd-108">Параметры области определения приложения можно изменить при создании приложения с помощью **конструктора проектов** или путем изменения файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="a51fd-108">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="a51fd-109">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a51fd-109">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a51fd-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a51fd-110">Example</span></span>  

 <span data-ttu-id="a51fd-111">В этом примере изменяется значение параметра пользователя `LastChanged`, а затем изменение сохраняется путем вызова метода `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="a51fd-111">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 [!code-vb[VbVbalrMyResources#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#5)]  
  
 <span data-ttu-id="a51fd-112">Для надлежащего выполнения этого примера приложение должно иметь пользовательский параметр `LastChanged` типа `Date`.</span><span class="sxs-lookup"><span data-stu-id="a51fd-112">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="a51fd-113">Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="a51fd-113">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51fd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a51fd-114">See also</span></span>

- [<span data-ttu-id="a51fd-115">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="a51fd-115">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="a51fd-116">Практическое руководство. Чтение параметров приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a51fd-116">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="a51fd-117">Практическое руководство. Изменение пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a51fd-117">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="a51fd-118">Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a51fd-118">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="a51fd-119">Управление параметрами приложения (.NET)</span><span class="sxs-lookup"><span data-stu-id="a51fd-119">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
