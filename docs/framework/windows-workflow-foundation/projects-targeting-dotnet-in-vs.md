---
title: Программирование Windows Forms в Visual Studio с помощью .NET Framework версий 3.0 и 3.5
ms.date: 03/30/2017
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
ms.openlocfilehash: 1469ce2906c1101bae4098cbcabd4a10a64c1c7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a>Программирование Windows Forms в Visual Studio с помощью .NET Framework версий 3.0 и 3.5
Можно использовать [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] для создания проектов, ориентированных на [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] версии 3.0 и 3.5. В этом разделе описано выполнение этой задачи.  
  
> [!NOTE]
>  При добавлении действий убедитесь, что задана необходимая версия [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Изменение целевой версии рабочего процесса после добавления действия приведет к ошибке проверки рабочего процесса.  
  
> [!WARNING]
>  Открытие существующих рабочих процессов в [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], включающих действия .Net Framework 3.5, приведет к возникновению ошибки в `this.SetValue()`. Чтобы открыть проекты, созданные с помощью предыдущих версий платформы .Net Framework, сначала необходимо открыть пустой рабочий процесс в конструкторе и добавить действие платформы .Net Framework 3.5.  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a>Создание проекта платформы .NET Framework 3.0 или 3.5 с помощью Visual Studio 2010  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Выберите **файл**, **новый**, **проекта**.  
  
3.  В раскрывающемся списке в верхней части диалогового окна выберите необходимую версию [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a>Обновление целевой версии платформы .NET Framework  
  
1.  Щелкните правой кнопкой мыши проект в обозревателе решений и выберите **свойства**.  
  
2.  В **требуемой версии .NET Framework** раскрывающегося списка выберите необходимую версию.
