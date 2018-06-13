---
title: Активация XAML
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517716"
---
# <a name="xaml-activation"></a>Активация XAML
В этом образце показано, как разместить декларативное бизнес-правило в IIS. Образец представляет базовый рабочий процесс с именем `EchoService`, в котором имеется одна операция.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на загрузки страницы, чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте решение XAMLActivation.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте решение, нажав клавишу **F5**.  
  
3.  Запустите файл WcfTestClient.exe. Введите в командной строке следующее:  
  
    1.  cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE  
  
    2.  Запустите файл WcfTestClient.exe.  
  
4.  Задать адрес службы в WcfTestClient.exe, нажав сочетание клавиш CTRL + SHIFT + A и установив для адреса службы http://localhost:56133/Service.xamlx.  
  
5.  Произведите операцию Echo для проверки службы.  
  
6.  Разверните службу в IIS, используя файл DeployToIIS.Bat из командной строки с правами администратора.  
  
7.  Обновите адрес службы в клиенте для http://localhost/XAMLActivation/Service.xamlx и проверьте службу, используя WcfTestClient.exe.
