---
title: 'Как выполнить: Считывание параметров во время выполнения с помощьюC#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974852"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a><span data-ttu-id="b307e-102">Как выполнить: Считывание параметров во время выполнения с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="b307e-102">How To: Read Settings at Run Time With C\#</span></span>

<span data-ttu-id="b307e-103">Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства".</span><span class="sxs-lookup"><span data-stu-id="b307e-103">You can read both Application-scoped and User-scoped settings at run time via the Properties object.</span></span> <span data-ttu-id="b307e-104">Объект "Свойства" предоставляет все параметры по умолчанию для проекта через элемент Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="b307e-104">The Properties object exposes all of the default settings for the project via the Properties.Settings.Default member.</span></span>  
  
## <a name="to-read-settings-at-run-time-with-c"></a><span data-ttu-id="b307e-105">Считывание параметров во время выполнения с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="b307e-105">To Read Settings at Run Time with C\#</span></span>
  
<span data-ttu-id="b307e-106">Доступ к соответствующему параметру через элемент Properties.Settings.Default.</span><span class="sxs-lookup"><span data-stu-id="b307e-106">Access the appropriate setting via the Properties.Settings.Default member.</span></span> <span data-ttu-id="b307e-107">В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor.</span><span class="sxs-lookup"><span data-stu-id="b307e-107">The following example shows how to assign a setting named `myColor` to a BackColor property.</span></span> <span data-ttu-id="b307e-108">Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`.</span><span class="sxs-lookup"><span data-stu-id="b307e-108">It requires you to have previously created a Settings file containing a setting named `myColor` of type `System.Drawing.Color`.</span></span> <span data-ttu-id="b307e-109">Сведения о создании файла параметров, см. в разделе [How To: Создание новых параметров во время разработки](how-to-create-a-new-setting-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="b307e-109">For information about creating a Settings file, see [How To: Create a New Setting at Design Time](how-to-create-a-new-setting-at-design-time.md).</span></span>  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b307e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b307e-110">See also</span></span>

- [<span data-ttu-id="b307e-111">Использование параметров приложения и параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="b307e-111">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="b307e-112">Практическое руководство. Написание параметров пользователя во время выполнения с помощьюC#</span><span class="sxs-lookup"><span data-stu-id="b307e-112">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)
- [<span data-ttu-id="b307e-113">Общие сведения о параметрах приложений</span><span class="sxs-lookup"><span data-stu-id="b307e-113">Application Settings Overview</span></span>](application-settings-overview.md)
