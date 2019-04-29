---
title: Использование параметров приложения и параметров пользователя
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: ea6994e653b3a06239634f5a0fddea84a07086e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777186"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="a69fe-102">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="a69fe-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="a69fe-103">Начиная с .NET Framework 2.0, можно создавать и получать доступ к значениям, которые сохраняются между сеансами выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="a69fe-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="a69fe-104">Эти значения называются *параметры*.</span><span class="sxs-lookup"><span data-stu-id="a69fe-104">These values are called *settings*.</span></span> <span data-ttu-id="a69fe-105">Параметры могут быть записаны пользовательские настройки или ценные сведения, необходимые приложению необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="a69fe-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="a69fe-106">Например можно создать ряд параметров, в которых хранятся настройки пользователя для цветовой схемы приложения.</span><span class="sxs-lookup"><span data-stu-id="a69fe-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="a69fe-107">Или можно сохранить строку подключения, указывающее базу данных, который использует приложение.</span><span class="sxs-lookup"><span data-stu-id="a69fe-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="a69fe-108">Параметры позволяют хранить данные, критически важные для приложения вне кода, а также создавать профили для хранения настроек разных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a69fe-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="a69fe-109">В этом разделе описываются способы использования параметров во время разработки и времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="a69fe-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a69fe-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a69fe-110">In This Section</span></span>  
 [<span data-ttu-id="a69fe-111">Практическое руководство. Создание новых параметров во время разработки</span><span class="sxs-lookup"><span data-stu-id="a69fe-111">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="a69fe-112">Объясняется, как использовать Visual Studio для создания нового значения для приложения.</span><span class="sxs-lookup"><span data-stu-id="a69fe-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="a69fe-113">Практическое руководство. Изменить значение существующего параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="a69fe-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="a69fe-114">В этой статье описывается использование Visual Studio, чтобы изменить значение существующего параметра.</span><span class="sxs-lookup"><span data-stu-id="a69fe-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="a69fe-115">Практическое руководство. Измените значение параметра между сеансами приложения</span><span class="sxs-lookup"><span data-stu-id="a69fe-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="a69fe-116">Подробные сведения изменить значение параметра в скомпилированном приложении между сеансами приложения.</span><span class="sxs-lookup"><span data-stu-id="a69fe-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="a69fe-117">Практическое руководство. Считывание параметров во время выполнения с помощьюC#</span><span class="sxs-lookup"><span data-stu-id="a69fe-117">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="a69fe-118">Описывает, как использовать код для чтения параметров с помощью C#.</span><span class="sxs-lookup"><span data-stu-id="a69fe-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="a69fe-119">Практическое руководство. Написание параметров пользователя во время выполнения с помощьюC#</span><span class="sxs-lookup"><span data-stu-id="a69fe-119">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="a69fe-120">Объясняет, как использовать код для записи и сохраните значения параметров пользователя с C#.</span><span class="sxs-lookup"><span data-stu-id="a69fe-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="a69fe-121">Практическое руководство. Добавить несколько наборов параметров в приложениеC#</span><span class="sxs-lookup"><span data-stu-id="a69fe-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="a69fe-122">Объясняется, как добавить несколько наборов параметров в приложение с C#.</span><span class="sxs-lookup"><span data-stu-id="a69fe-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69fe-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a69fe-123">See also</span></span>

- [<span data-ttu-id="a69fe-124">Параметры приложения для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a69fe-124">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
