---
title: "Влияние изменения внешнего вида базовой формы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b808d10cd393d84ed29cb5e1cccfcff9c6c098d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a>Влияние изменения внешнего вида базовой формы
В процессе разработки приложения часто может потребоваться изменить внешний вид базовой формы, от которой наследуются другие формы проекта (или других проектов).  
  
 Во время разработки изменения внешнего вида базовой формы (будь то значения свойств либо добавление и удаление элементов управления) отражаются на наследуемых формах при построении проекта, содержащего базовую форму. Просто сохранить изменения в базовой форме будет недостаточно. Для сборки проекта выберите в меню **Сборка** пункт **Собрать**.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Изменения, внесенные в базовую форму во время выполнения, не влияют на наследуемые формы, экземпляры которых уже созданы.  
  
## <a name="see-also"></a>См. также  
 [base](~/docs/csharp/language-reference/keywords/base.md)  
 [Практическое руководство. Наследование форм Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Визуальное наследование в Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
