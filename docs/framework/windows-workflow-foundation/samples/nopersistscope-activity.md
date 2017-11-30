---
title: "Действие NoPersistScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8813739f9e2f22cb94ed353f73a64562d3aeaa84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="nopersistscope-activity"></a>Действие NoPersistScope
В этом образце показано, как обрабатывать несериализуемое и высвобождаемое состояние в рабочем процессе. Важно заметить, что попыток сохранения несериализуемого состояния в рабочих процессах не происходит. Кроме того, необходимо очищать высвобождаемые объекты после их использования в рабочем процессе.  
  
## <a name="demonstrates"></a>Демонстрации  
 Настраиваемое действие `NoPersistScope` и его конструктор.  
  
## <a name="using-the-nopersistzone-activity"></a>Использование действия NoPersistZone  
 При запуске данного образца рабочего процесса пользовательское действие `CreateTextWriter` создает объект типа <xref:System.IO.TextWriter> и сохраняет его в переменной рабочего процесса. Параметр <xref:System.IO.TextWriter> является объектом <xref:System.IDisposable>. Данный модуль записи <xref:System.IO.TextWriter>, настроенный на запись в файл "out.txt" в директории, из которой запущен образец, используется действием <xref:System.Activities.Statements.WriteLine>, когда оно копирует какой-либо текст, вводимый с консоли.  
  
 Логика копирования действует в рамках действия `NoPersistScope` (код для которого также является частью данного образца), что препятствует сохранению рабочего процесса. При вводе в `unload` на консоль, узел попытается сохранить экземпляр рабочего процесса, но время ожидания для этой операции, поскольку рабочий процесс остается в `NoPersistScope`. Рабочий процесс также применяет настраиваемое действие под названием `Dispose`, чтобы удалить объект <xref:System.IO.TextWriter>, когда он больше не нужен. Действие `Dispose` помещается в блоке <xref:System.Activities.Statements.TryCatch.Finally%2A> действия <xref:System.Activities.Statements.TryCatch>, в котором объявляется переменная <xref:System.IO.TextWriter>, чтобы гарантировать ее запуск даже при формировании исключения в ходе работы блока Try.  
  
 Можно ввести в `exit` для экземпляра рабочего процесса завершения работы программы.  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте решение NoPersistZone.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.  
  
3.  После успешного построения нажмите клавишу F5 или выберите **начать отладку** из **отладки** меню или нажмите клавиши CTRL + F5 или выберите **Запуск без отладки** из **Отладки** меню для запуска без отладки.  
  
#### <a name="to-cleanup-optional"></a>Очистка (необязательно)  
  
1.  Для удаления хранилища экземпляров SQL запустите команду Cleanup.cmd.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`  
  
## <a name="see-also"></a>См. также
