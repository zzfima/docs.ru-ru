---
title: "Практическое руководство. Использование моникера службы с контрактами WSDL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c44b09f512a7625360ca5036316d03a4602c5186
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Практическое руководство. Использование моникера службы с контрактами WSDL
Существуют ситуации, когда требуется полностью автономный клиент COM-взаимодействия. Например, вызываемая служба может не отображать конечную точку обмена метаданными, а клиентская библиотека WCF может быть не зарегистрирована для COM-взаимодействия. В таких ситуациях можно создать WSDL-файл, описывающий службу, и передать его в моникер службы WCF. В данном разделе описывается, как вызвать образец WCF "Приступая к работе" с помощью моникера WSDL для службы WCF.  
  
### <a name="using-the-wsdl-service-moniker"></a>Использование моникера WSDL  
  
1.  Откройте и постройте образец решения "Приступая к работе".  
  
2.  Откройте Internet Explorer и перейдите по адресу http://localhost/ServiceModelSamples/Service.svc, чтобы убедиться в том, что служба работает.  
  
3.  В файле Service.cs добавьте следующий атрибут в класс CalculatorService:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  Добавьте пространство имен привязки в файл конфигурации службы App.config:  
  
  
  
5.  Создайте WSDL-файл для считывания приложением. Поскольку пространства имен были добавлены на шагах 3 и 4, можно использовать IE для запроса всего описания WSDL для службы. Для этого перейдите по адресу http://localhost/ServiceModelSamples/Service.svc?wsdl. Файл из Internet Explorer можно сохранить с именем serviceWSDL.xml. Если на шагах 3 и 4 не было указано пространство имен, документ WSDL, возвращаемый после запроса вышеуказанного URL-адреса, будет не полным. Возвращаемый документ WSDL будет содержать несколько операторов импорта, с помощью которых выполняется импорт других документов WSDL. Необходимо пройти все операторы импорта и построить полный документ WSDL, объединяющий как данные, полученные из службы, так и импортированные документы WSDL.  
  
6.  Откройте Visual Basic 6.0 и создайте новый стандартный EXE-файл. Добавьте в форму кнопку и дважды щелкните ее, чтобы добавить следующий код в обработчик щелчка.  
  
    ```  
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    >  Если неправильно сформирован моникер или служба недоступна, при вызове `GetObject` будет получена ошибка "Синтаксическая ошибка".  При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
7.  Запустите приложение Visual Basic 6.0. Отобразится окно сообщения с результатами вызова Subtract(145, 76.54).  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Интеграция с Общие сведения о приложениях COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
