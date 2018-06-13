---
title: Простой класс TransactionScope
ms.date: 03/30/2017
ms.assetid: 1e22b76a-76de-43b4-9be7-7a86ed3d5a44
ms.openlocfilehash: fe6877c4b2d72dc3d571740395fd4dc92ca8e99c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516806"
---
# <a name="basic-transactionscope"></a>Простой класс TransactionScope
Этот образец состоит из четырех сценариев, выполнение которых демонстрирует вкладывание экземпляров <xref:System.Activities.Statements.TransactionScope>. В первом сценарии показана вложенность стороннего действия, о разработке которого автору ничего не известно. Второй и третий сценарии показывают, как соблюдаются времена ожиданий, а последний сценарий показывает настройку <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>.  
  
## <a name="nesting-of-transactionscopeactivity"></a>Вложенность действия TransactionScopeActivity  
 Рабочий процесс для первого сценария состоит из двух последовательных действий <xref:System.Activities.Statements.WriteLine>, за которыми следует <xref:System.Activities.Statements.TransactionScope>. Текст диапазона <xref:System.Activities.Statements.TransactionScope> представляет собой последовательность еще двух действий <xref:System.Activities.Statements.WriteLine>, пользовательского действия, которое выводит локальный идентификатор транзакции, и стороннего действия. Стороннее действие `TransactionScopeTest` содержит объект <xref:System.Activities.Statements.TransactionScope>, хотя автору рабочего процесса об этом не может быть известно. В этом сценарии показывается, что действия <xref:System.Activities.Statements.TransactionScope> могут быть вложенными.  
  
## <a name="time-outs"></a>Время ожидания  
 Рабочий процесс для второго сценария практически совпадает с рабочим процессом для первого сценария. Класс `TransactionScopeTest` заменен классом <xref:System.Activities.Statements.TransactionScope>. У текста <xref:System.Activities.Statements.TransactionScope> задержка составляет пять секунд, а время ожидания для транзакции равно двум секундам. Время ожидания для внешней области <xref:System.Activities.Statements.TransactionScope> составляет 10 секунд. Обратите внимание, что учитывается наименьшее время ожидания, заданное для области, и время ожидания транзакции заканчивается.  
  
 Рабочий процесс для третьего сценария очень похож на второй сценарий. Действие задержки перемещено из текста внутренней <xref:System.Activities.Statements.TransactionScope> и поставлено сразу после него в последовательность, которая является телом внешнего класса. <xref:System.Activities.Statements.TransactionScope>. Время ожидания транзакции по-прежнему истекает, но это происходит потому, что двухсекундное время ожидания внутреннего класса <xref:System.Activities.Statements.TransactionScope> уже не применяется. Время ожидания транзакции заканчивается через 10 секунд, когда время ожидания внешнего класса <xref:System.Activities.Statements.TransactionScope> уже превышено.  
  
## <a name="aborting-on-transaction-failure"></a>Прерывание по сбою транзакции  
 Этот рабочий процесс похож на третий сценарий, за исключением того, что время ожидания заменено свойством <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>. Обратите внимание, что флаги всех внутренних дочерних элементов, если они заданы, должны соответствовать внешней области <xref:System.Activities.Statements.TransactionScope>. В этом сценарии такого соответствия нет, поэтому при открытии рабочего процесса возникает исключение.  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте решение BasicTransactionScopeSample.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.  
  
3.  После успешного построения нажмите клавишу F5 или выберите **начать отладку** из **отладки** меню. Также нажмите клавиши CTRL + F5 или выбрать команду **Запуск без отладки** из **отладки** меню для запуска без отладки.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\BasicTransactionScope`