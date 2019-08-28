---
title: Загрузка из XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: 2f45beb398e6d6b91bf7444dd590b862ff8c7515
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038089"
---
# <a name="load-from-xaml"></a>Загрузка из XAML
В этом образце показан способ динамической загрузки рабочего процесса XAML без применения средства XamlBuildTask. Вместо этого в образце вызывается метод <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>. Пример представляет собой клиентское приложение Windows Presentation Foundation (WPF), которое загружает рабочие процессы <xref:System.Activities.XamlIntegration.ActivityXamlServices> XAML с помощью класса и выполняет их. После загрузки этих процессов с использованием класса <xref:System.Activities.XamlIntegration.ActivityXamlServices> возвращается действие <xref:System.Activities.DynamicActivity%601>, которое может быть выполнено.

#### <a name="to-use-this-sample"></a>Использование этого образца

1. С помощью Visual Studio 2010 откройте файл решения Лоадфромксамл. sln.

2. Для построения решения нажмите CTRL+SHIFT+B.

3. Чтобы запустить решение, нажмите клавиши CTRL+F5.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
