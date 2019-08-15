---
title: Как Создание нового параметра во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 35a7cd8cc1daaf76a25977751ddc9ec0709e5947
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037904"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="e4f9e-102">Как Создать новый параметр во время разработки</span><span class="sxs-lookup"><span data-stu-id="e4f9e-102">How To: Create a new setting at design time</span></span>

<span data-ttu-id="e4f9e-103">Новый параметр можно создать во время разработки с помощью конструктора параметров в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-103">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="e4f9e-104">Конструктор параметров — это интерфейс в стиле сетки, позволяющий создавать новые параметры и задавать свойства этих параметров.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="e4f9e-105">Для новых параметров необходимо указать имя, значение, тип и область.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="e4f9e-106">После создания параметра он доступен в коде.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-106">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="e4f9e-107">Создание нового параметра во время разработки в C\#</span><span class="sxs-lookup"><span data-stu-id="e4f9e-107">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="e4f9e-108">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-108">Open Visual Studio.</span></span>

2. <span data-ttu-id="e4f9e-109">В **Обозреватель решений**разверните узел **свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-109">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="e4f9e-110">Дважды щелкните файл. Settings, в который нужно добавить новый параметр.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-110">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="e4f9e-111">По умолчанию для этого файла используется имя Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-111">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="e4f9e-112">В конструкторе параметров задайте **имя**, **значение**, **тип**и **область** для параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-112">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="e4f9e-113">Каждая строка представляет отдельный параметр.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-113">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="e4f9e-114">Создание нового параметра во время разработки в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4f9e-114">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="e4f9e-115">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="e4f9e-116">В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-116">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="e4f9e-117">На странице **Свойства** перейдите на вкладку **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="e4f9e-117">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="e4f9e-118">В конструкторе параметров задайте **имя**, **значение**, **тип**и **область** для параметра.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-118">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="e4f9e-119">Каждая строка представляет отдельный параметр.</span><span class="sxs-lookup"><span data-stu-id="e4f9e-119">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4f9e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e4f9e-120">See also</span></span>

- [<span data-ttu-id="e4f9e-121">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="e4f9e-121">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="e4f9e-122">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="e4f9e-122">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="e4f9e-123">Практическое руководство. Изменение значения существующего параметра во время разработки</span><span class="sxs-lookup"><span data-stu-id="e4f9e-123">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
