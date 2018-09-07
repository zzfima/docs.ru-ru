---
title: Дополнительная политика
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: becdc28affd877239474d6f0f007a480297bccb8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083794"
---
# <a name="advanced-policy"></a>Дополнительная политика
Данный образец выступает как дополнение образца простой политики. К правилам для скидок на жилье и коммерческих скидок, описанных в примере простой политики, добавлены несколько новых правил.  
  
 Добавлено правило высокой стоимости, которое предоставляет большую скидку на заказы высокой стоимости. Это правило имеет более низкий приоритет, чем предыдущие два правила, чтобы повторно записывать поля скидки и быть приоритетными по отношению к правилам для скидок на жилье и коммерческих скидок.  
  
 Также добавлено правило расчета общей суммы, которое выполняет вычисление общей суммы в зависимости от уровня скидки. Он демонстрирует создание ссылки на метод, определенный для действия рабочего процесса, а также использование остальных действий. Данное правило также демонстрирует поведение последовательного соединения, поскольку его вычисление будет выполняться каждый раз при изменении полей скидки. Кроме того, показано назначение для метода "CalculateTotal" атрибута "RuleWriteAttribute". По этим причинам для связанных правил (ErrorTotalRule) при каждом выполнении метода выполняется повторное вычисление.  
  
 Последнее добавленное правило отвечает за обнаружение ошибок (в данном случае «Общая сумма меньше 0»). В этом случае выполнение политики приостанавливается.  
  
 И наконец, вызовы метода `Console.Writeline` добавлены как действия для каждого правила, которые помогают сделать выполнение правила более видимым, одновременно демонстрируя возможность доступа к статическим методам для ссылочных типов. Также можно использовать отслеживание, чтобы повысить видимость выполняемых правил.  
  
 В данном образце используются приведенные ниже правила.  
  
 **ResidentialDiscountRule:**  
  
 IF OrderValue > 500 AND CustomerType = Residential  
  
 THEN Discount = 5%  
  
 **BusinessDiscountRule:**  
  
 IF OrderValue > 10000 AND CustomerType = Business  
  
 THEN Discount = 10%  
  
 **HighValueDiscountRule:**  
  
 IF OrderValue > 20000  
  
 THEN Discount = 15%  
  
 **TotalRule:**  
  
 IF Discount > 0  
  
 THEN CalculateTotal(OrderValue, Discount)  
  
 ELSE Total = OrderValue  
  
 **ErrorTotalRule:**  
  
 Если общее \< 0  
  
 THEN Error = "Fired ErrorTotalRule"; Halt  
  
 Вычисление и выполнение правила также можно просмотреть посредством трассировки и отслеживания.  
  
### <a name="to-build-the-sample"></a>Сборка образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.  
  
3.  Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Выполнение образца  
  
-   В окне командной строки пакета SDK запустите файл с расширением EXE в папке «AdvancedPolicy\bin\debug» (или в папке «AdvancedPolicy\bin» для образца в Visual Basic), вложенной в главную папку образца.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец находится в следующем каталоге:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Простая политика](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
