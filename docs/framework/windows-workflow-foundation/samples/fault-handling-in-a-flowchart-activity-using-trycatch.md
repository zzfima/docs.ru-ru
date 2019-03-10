---
title: Обработка ошибок в действии блок-схемы с помощью TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 3f45d4a60de3201a3100fba3af6cc15484a1fbf0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708838"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Обработка ошибок в действии блок-схемы с помощью TryCatch
В этом образце показано использование действия <xref:System.Activities.Statements.TryCatch> в рамках действия сложного потока управления.

 В этом образце промокод и несколько дочерних элементов передаются как переменные в действие <xref:System.Activities.Statements.Flowchart>, которое вычисляет скидку на основе формулы, которая соответствует промокоду. Образец включает императивный код и версии конструктора рабочих процессов образца.

 В следующей таблице представлены переменные для действия `CreateFlowchartWithFaults`.

|Параметры|Описание|
|----------------|-----------------|
|promoCode|Промокод. Тип: String<br /><br /> Возможные значения с описанием в скобках.<br /><br /> -Одним (один)<br />-MNK (женат, детей нет.)<br />-MWK (женат детей).|
|numKids|Число детей. Тип: int|

 Действие `CreateFlowchartWithFaults` использует действие <xref:System.Activities.Statements.FlowSwitch%601>, которое производит переключения на аргументе `promoCode` и вычисляет скидку с использованием следующей формулы.

|Значение `promoCode`|Скидка (%)|
|--------------------------|--------------------|
|Single|10|
|MNK|15|
|MWK|15 + (1 – 1 /`numberOfKids`)\*10 **Примечание:**  Это вычисление может вызвать исключение <xref:System.DivideByZeroException>. Поэтому вычисление скидки упаковано в действие <xref:System.Activities.Statements.TryCatch>, которое кэширует исключение <xref:System.DivideByZeroException> и устанавливает скидку в нуль.|

#### <a name="to-use-this-sample"></a>Использование этого образца

1.  Откройте файл решения FlowchartWithFaultHandling.sln в Visual Studio 2010.

2.  Для построения решения нажмите CTRL+SHIFT+B.

3.  Чтобы запустить решение, нажмите клавишу F5.

> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a>См. также
- [Рабочие процессы с блок-схемой](../flowchart-workflows.md)
- [Исключения](../exceptions.md)
