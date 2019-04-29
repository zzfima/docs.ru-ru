---
title: 'Как выполнить: Написание параметров пользователя во время выполнения с помощью C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 264fa9706f9255d7324cad6d02c36cc424e28995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778837"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a><span data-ttu-id="5a38b-102">Как выполнить: Написание параметров пользователя во время выполнения с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="5a38b-102">How To: Write User Settings at Run Time with C\#</span></span>

<span data-ttu-id="5a38b-103">Параметры с областью действия приложения доступны только для чтения. Их можно изменить только во время разработки или путем изменения CONFIG-файла между сеансами приложения.</span><span class="sxs-lookup"><span data-stu-id="5a38b-103">Settings that are application-scoped are read-only, and can only be changed at design time or by altering the .config file in between application sessions.</span></span> <span data-ttu-id="5a38b-104">Параметры, имеющие область действия пользователя, однако, можно записывать во время выполнения так же, как значение любого свойства.</span><span class="sxs-lookup"><span data-stu-id="5a38b-104">Settings that are user-scoped, however, can be written at run time just as you would change any property value.</span></span> <span data-ttu-id="5a38b-105">Новое значение сохраняется в течение всего сеанса приложения.</span><span class="sxs-lookup"><span data-stu-id="5a38b-105">The new value persists for the duration of the application session.</span></span> <span data-ttu-id="5a38b-106">Для сохранения изменений параметров между сеансами приложения вызовите метод Save.</span><span class="sxs-lookup"><span data-stu-id="5a38b-106">You can persist the changes to the settings between application sessions by calling the Save method.</span></span>  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a><span data-ttu-id="5a38b-107">Как выполнить: Запись и сохранение пользовательских параметров во время выполнения с помощью c#\#</span><span class="sxs-lookup"><span data-stu-id="5a38b-107">How To: Write and Persist User Settings at Run Time with C\#</span></span>
  
1. <span data-ttu-id="5a38b-108">Получите доступ к параметру и присвойте ему новое значение, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="5a38b-108">Access the setting and assign it a new value as shown in this example:</span></span>  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. <span data-ttu-id="5a38b-109">Если необходимо сохранять изменения параметров между сеансами приложения, вызовите метод Save, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5a38b-109">If you want to persist the changes to the settings between application sessions, call the Save method as shown in this example:</span></span>  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
<span data-ttu-id="5a38b-110">Параметры пользователя сохраняются в файле в папке, вложенной в скрытую локальную папку данных приложения.</span><span class="sxs-lookup"><span data-stu-id="5a38b-110">User settings are saved in a file within a subfolder of the user’s local hidden application data folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a38b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="5a38b-111">See also</span></span>

- [<span data-ttu-id="5a38b-112">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="5a38b-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="5a38b-113">Практическое руководство. Считывание параметров во время выполнения с помощьюC#</span><span class="sxs-lookup"><span data-stu-id="5a38b-113">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="5a38b-114">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="5a38b-114">Application Settings Overview</span></span>](application-settings-overview.md)
