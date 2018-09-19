---
title: Использование ExpressionTextBox в пользовательском конструкторе действия
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: 34a2d7b2217fb5ce072ad4bc243022ec27828af1
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45991607"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Использование ExpressionTextBox в пользовательском конструкторе действия
В этом образце показано, как использовать <xref:System.Activities.Presentation.View.ExpressionTextBox> в настраиваемом конструкторе действий. Пользовательское действие `MultiAssign` присваивает два строковых значения двум строковым переменным. Некоторые элементы управления <xref:System.Activities.Presentation.View.ExpressionTextBox> привязываются к аргументу <xref:System.Activities.InArgument>, а некоторые - к аргументу <xref:System.Activities.OutArgument>.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 `ArgumentToExpressionConverter` - это преобразователь типов, используемый для привязки выражений к аргументам. Параметр `ConverterParameter` необходимо установить в соответствующее значение `In` или `Out`. Тип `InOut` не поддерживается.  
  
 `UseLocationExpression` Атрибут используется на `OutArgument`, чтобы указать, что выражение должно быть выражение L-значение («левое значение» или «значение расположения»). В большинстве случаев левостороннее выражение является допустимым идентификатором Visual Basic, используемым для указания того, что возвращаемый аргумент `OutArgument` является переменной или именем аргумента.  
  
 В этом примере для атрибута `MaxLines` установлено значение 1, а значение атрибута `MinLines` не задано. Это указывает, что текстовое поле <xref:System.Activities.Presentation.View.ExpressionTextBox> имеет фиксированный размер в одну строку независимо от объема текста, введенного пользователем. Чтобы разрешить изменение размера текстового поля <xref:System.Activities.Presentation.View.ExpressionTextBox> в соответствии с объемом вводимых пользователем данных, задайте значение `MaxLines`, которое больше значения `MinLines`.  
  
 Текстовое поле ExpressionTextBox может быть привязано только к аргументам и не может быть привязано к свойствам CLR.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл ExpressionTextBoxSample.sln с помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
#### <a name="to-run-this-sample"></a>Запуск образца  
  
1.  Добавьте в решение новое консольное приложение рабочего процесса.  
  
2.  Добавьте ссылку на **ExpressionTextBoxSample** проекта из нового проекта консольного приложения рабочего процесса.  
  
3.  Постройте решение.  
  
4.  Перетащите **MultiAssign** из области элементов и поместите его в рабочий процесс.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [Разработка приложений с помощью конструктора рабочего процесса](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
