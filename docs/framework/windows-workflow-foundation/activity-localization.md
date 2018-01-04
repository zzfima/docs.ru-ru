---
title: "Локализация действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccabcda9e26751db80ee7e955458d0eee0cae7e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="activity-localization"></a><span data-ttu-id="eb872-102">Локализация действий</span><span class="sxs-lookup"><span data-stu-id="eb872-102">Activity Localization</span></span>
<span data-ttu-id="eb872-103">Если приложения и компоненты рабочего процесса могут подлежать локализации для других языков и адаптации к особенностям других регионов, то в них следует использовать строки ресурсов, чтобы локализацию можно было провести без перекомпилирования.</span><span class="sxs-lookup"><span data-stu-id="eb872-103">When workflow applications and components have the potential to be localized into other cultures and languages, resource strings should be used so that they can be localized without recompiling.</span></span>  
  
## <a name="activity-localization"></a><span data-ttu-id="eb872-104">Локализация действий</span><span class="sxs-lookup"><span data-stu-id="eb872-104">Activity Localization</span></span>  
 <span data-ttu-id="eb872-105">Как и при работе со всеми локализуемыми приложениями (выпускаемыми в различных версиях для различных языков и различных региональных стандартов), все отображаемые пользователю строки должны храниться в файле ресурсов, а не находиться в коде.</span><span class="sxs-lookup"><span data-stu-id="eb872-105">As with all applications that must be localized (released in different versions for different languages and cultures), any strings that are displayed to the user should not be put directly in code, but rather stored in a resource file.</span></span> <span data-ttu-id="eb872-106">Строки может осуществляться через <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span><span class="sxs-lookup"><span data-stu-id="eb872-106">The strings can then be accessed through <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`.</span></span> <span data-ttu-id="eb872-107">При разработке компонента, распространяемого на различных языках, строки ресурсов также следует применять для сообщений проверки допустимости действий, определяемых пользователем данных отслеживания, сообщений трассировки и сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="eb872-107">If you are developing a component that is distributed in several languages, you also want to use resource strings for activity validation messages, user-defined tracking data, tracing messages, and error messages as well.</span></span>  
  
 <span data-ttu-id="eb872-108">В следующем примере демонстрируется применение файла ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eb872-108">The following exercise demonstrates how to use a resource file.</span></span>  
  
#### <a name="using-resource-files-for-localized-strings"></a><span data-ttu-id="eb872-109">Использование файлов ресурсов для локализованных строк</span><span class="sxs-lookup"><span data-stu-id="eb872-109">Using resource files for localized strings</span></span>  
  
1.  <span data-ttu-id="eb872-110">В [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **добавить...** , **Новый элемент...** .</span><span class="sxs-lookup"><span data-stu-id="eb872-110">In [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], right-click your project in **Solution Explorer** and select **Add…**, **New Item…**.</span></span>  
  
2.  <span data-ttu-id="eb872-111">Выберите **файл ресурсов** и назовите файл ErrorResources.resx.</span><span class="sxs-lookup"><span data-stu-id="eb872-111">Select **Resources File** and name the file ErrorResources.resx.</span></span> <span data-ttu-id="eb872-112">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eb872-112">Click **Add**.</span></span>  
  
3.  <span data-ttu-id="eb872-113">Откройте файл ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eb872-113">Open the resource file.</span></span> <span data-ttu-id="eb872-114">Добавить новую запись с **имя** из ErrorString и **значение** из «действие недопустимо.»</span><span class="sxs-lookup"><span data-stu-id="eb872-114">Add a new entry with a **Name** of ErrorString and a **Value** of "The activity is not valid."</span></span>  
  
4.  <span data-ttu-id="eb872-115">Добавьте к классу следующие инструкции `using`.</span><span class="sxs-lookup"><span data-stu-id="eb872-115">Add the following `using` statements to your class.</span></span>  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
    ```  
  
5.  <span data-ttu-id="eb872-116">Создайте в проекте диспетчер ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eb872-116">Create a resource manager in your project.</span></span>  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
    ```  
  
6.  <span data-ttu-id="eb872-117">При необходимости строку можно получать из диспетчера ресурсов.</span><span class="sxs-lookup"><span data-stu-id="eb872-117">Get the string from the resource manager where it is required.</span></span>  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
    ```  
  
 <span data-ttu-id="eb872-118">В следующем образце кода показано использование локализованных строк в методе <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb872-118">The following code sample demonstrates how to utilize localized strings in the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span>  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```
