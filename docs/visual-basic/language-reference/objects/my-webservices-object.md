---
title: Объект My.WebServices
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 290d025985663bc45fe605a2e9904fc90fb2bc63
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350341"
---
# <a name="mywebservices-object"></a>Объект My.WebServices
Предоставляет свойства для создания и доступа к одному экземпляру каждой веб-службы XML, на которую ссылается текущий проект.  
  
## <a name="remarks"></a>Примечания  
 Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект. Каждый экземпляр создается по запросу. Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`. Имя свойства совпадает с именем веб-службы, к которой обращается свойство. Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой. Сведения о добавлении веб-служб в проект см. в разделе [доступ к веб-службам приложений](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Объект `My.WebServices` предоставляет только веб-службы, связанные с текущим проектом. Он не предоставляет доступ к веб-службам, объявленным в упоминаемых в них библиотеках DLL. Для доступа к веб-службе, предоставляемой библиотекой DLL, необходимо использовать полное имя веб-службы в формате *dllname*. *WebServiceName*. Дополнительные сведения см. в разделе [доступ к веб-службам приложений](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Объект и его свойства недоступны для веб-приложений.  
  
## <a name="properties"></a>Свойства  
 Каждое свойство объекта `My.WebServices` предоставляет доступ к экземпляру веб-службы, на которую ссылается текущий проект. Имя свойства совпадает с именем веб-службы, к которой обращается свойство, а тип свойства совпадает с типом веб-службы.  
  
> [!NOTE]
> При конфликте имен имя свойства для доступа к веб-службе — *RootNamespace*_*Namespace*\_*ServiceName*. Например, рассмотрим две веб-службы с именем `Service1`. Если одна из этих служб находится в корневом пространстве имен `WindowsApplication1` и в `Namespace1`пространства имен, доступ к этой службе будет осуществляться с помощью `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 При первом доступе к одному из свойств объекта `My.WebServices` он создает новый экземпляр веб-службы и сохраняет его. Последующие обращения к этому свойству возвращают этот экземпляр веб-службы.  
  
 Вы можете удалить веб-службу, назначив `Nothing` свойству для этой веб-службы. Метод задания свойства присваивает `Nothing` сохраненному значению. Если присвоить свойству любое значение, отличное от `Nothing`, то метод задания выдаст исключение <xref:System.ArgumentException>.  
  
 Проверить, сохраняет ли свойство объекта `My.WebServices` экземпляр веб-службы, можно с помощью оператора `Is` или `IsNot`. С помощью этих операторов можно проверить, является ли значение свойства `Nothing`.  
  
> [!NOTE]
> Как правило, оператор `Is` или `IsNot` должен считывать значение свойства для выполнения сравнения. Однако если свойство в настоящее время хранит `Nothing`, свойство создает новый экземпляр веб-службы, а затем возвращает этот экземпляр. Однако компилятор Visual Basic обрабатывает свойства объекта `My.WebServices` особым образом и позволяет оператору `Is` или `IsNot` проверять состояние свойства без изменения его значения.  
  
## <a name="example"></a>Пример  
 В этом примере вызывается метод `FahrenheitToCelsius` веб-службы `TemperatureConverter` XML и возвращается результат.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 Чтобы этот пример работал, проект должен ссылаться на веб-службу с именем `Converter`, и эта веб-служба должна предоставлять метод `ConvertTemperature`. Дополнительные сведения см. в разделе [доступ к веб-службам приложений](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 Этот код не работает в проекте веб-приложения.  
  
## <a name="requirements"></a>Требования  
  
### <a name="availability-by-project-type"></a>Доступность по типу проекта  
  
|Тип проекта|Доступно|  
|---|---|  
|Приложение Windows|**Да**|  
|Библиотека классов|**Да**|  
|Консольное приложение|**Да**|  
|Библиотека элементов управления Windows|**Да**|  
|Библиотека веб-элементов управления|**Да**|  
|Службы Windows|**Да**|  
|Веб-сайт|Нет|  
  
## <a name="see-also"></a>См. также

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [Доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
