---
title: Использование параметров приложения и параметров пользователя
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: f5231ecc9fb3898d60241ea8a53b509daced8a0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="8eeba-102">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="8eeba-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="8eeba-103">Начиная с .NET Framework 2.0, можно создать и доступа к значениям, которые сохраняются между сеансами выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="8eeba-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="8eeba-104">Эти значения называются *параметры*.</span><span class="sxs-lookup"><span data-stu-id="8eeba-104">These values are called *settings*.</span></span> <span data-ttu-id="8eeba-105">Параметры могут представлять настройки пользователя или ценные сведения, необходимые приложению необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="8eeba-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="8eeba-106">Например можно создать ряд параметров, в которых хранятся настройки пользователя для цветовой схемы приложения.</span><span class="sxs-lookup"><span data-stu-id="8eeba-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="8eeba-107">Или может сохранить строку подключения, указывающее базу данных, которую использует приложение.</span><span class="sxs-lookup"><span data-stu-id="8eeba-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="8eeba-108">Параметры позволяют хранить сведения, необходимые для приложения вне кода и создавать профили для хранения настроек отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="8eeba-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="8eeba-109">В этом разделе описываются способы использования параметров во время разработки и во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8eeba-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8eeba-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8eeba-110">In This Section</span></span>  
 [<span data-ttu-id="8eeba-111">Практическое руководство. Создание новых параметров во время разработки</span><span class="sxs-lookup"><span data-stu-id="8eeba-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="8eeba-112">Объясняется, как использовать Visual Studio для создания нового значения для приложения.</span><span class="sxs-lookup"><span data-stu-id="8eeba-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="8eeba-113">Практическое руководство. Изменение значения существующего параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="8eeba-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="8eeba-114">Описывает, как использовать Visual Studio, чтобы изменить значение существующего параметра.</span><span class="sxs-lookup"><span data-stu-id="8eeba-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="8eeba-115">Практическое руководство. Изменение значение параметра в промежутке между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="8eeba-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="8eeba-116">Дополнительные сведения об изменении значения параметра в скомпилированном приложении между сеансами приложения.</span><span class="sxs-lookup"><span data-stu-id="8eeba-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="8eeba-117">Практическое руководство. Считывание параметров во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="8eeba-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="8eeba-118">Описывает, как использовать код для чтения параметров с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="8eeba-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="8eeba-119">Практическое руководство. Написание параметров пользователя во время выполнения с помощью C#</span><span class="sxs-lookup"><span data-stu-id="8eeba-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="8eeba-120">Объясняется, как использовать код для записи и сохранения значений параметров пользователя с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="8eeba-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="8eeba-121">Практическое руководство. Добавление несколько наборов параметров в приложение на C#</span><span class="sxs-lookup"><span data-stu-id="8eeba-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="8eeba-122">Сведения о том, как добавить несколько наборов параметров в приложение с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="8eeba-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eeba-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8eeba-123">See Also</span></span>  
 [<span data-ttu-id="8eeba-124">Параметры приложения для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8eeba-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)
