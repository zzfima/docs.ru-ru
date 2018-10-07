---
title: Как предоставить доступ к каналу в форматах Atom и RSS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
ms.openlocfilehash: 6b26dabb9ed5c2c7bb2410dc1e844add6a69bdf3
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842727"
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a>Как предоставить доступ к каналу в форматах Atom и RSS
Windows Communication Foundation (WCF) позволяет создавать службы, которая предоставляет веб-канала синдикации. В этом разделе рассматривается процесс создания службы синдикации, предоставляющей веб-канал синдикации с помощью Atom 1.0 и RSS 2.0. Эта служба предоставляет одну конечную точку, которая может вернуть любой формат синдикации. В целях упрощения в данном образце используется резидентная служба. В рабочей среде служба такого типа размещается в IIS или WAS. Дополнительные сведения о различных вариантах размещения WCF, см. в разделе [размещения](../../../../docs/framework/wcf/feature-details/hosting.md).  
  
### <a name="to-create-a-basic-syndication-service"></a>Создание базовой службы синдикации  
  
1.  Определите контракт службы с помощью интерфейса, отмеченного атрибутом <xref:System.ServiceModel.Web.WebGetAttribute>. Каждая операция, предоставляемая как веб-канал синдикации, возвращает объект <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Обратите внимание на параметры для <xref:System.ServiceModel.Web.WebGetAttribute>. `UriTemplate` указывает URL-адрес, используемый для вызова этой операции службы. Строка для этого параметра содержит литералы и переменные в фигурных скобках ({*формат*}). Эта переменная соответствует параметру `format` операции службы. Дополнительные сведения см. в разделе <xref:System.UriTemplate>. `BodyStyle` влияет на способ записи сообщений, отправляемых и получаемых этой операцией службы. <xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> указывает, что данные, отправляемые и получаемые этой операцией службы, не заключаются в оболочку из XML-элементов, определенных в инфраструктуре. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Web.WebMessageBodyStyle>.  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    >  Используйте атрибут <xref:System.ServiceModel.ServiceKnownTypeAttribute>, чтобы задать, какие типы возвращаются операциями службы в этом интерфейсе.  
  
2.  Реализуйте контракт службы.  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3.  Создайте объект <xref:System.ServiceModel.Syndication.SyndicationFeed>, затем добавьте автора, категорию и описание.  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4.  Создайте несколько объектов <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5.  Добавьте объекты <xref:System.ServiceModel.Syndication.SyndicationItem> в веб-канал.  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6.  Используйте параметр формата, чтобы был возвращен необходимый формат.  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a>Размещение службы  
  
1.  Создание объекта <xref:System.ServiceModel.Web.WebServiceHost>. Класс <xref:System.ServiceModel.Web.WebServiceHost> автоматически добавляет конечную точку по базовому адресу службы, если конечная точка не указана ни в коде, ни в конфигурации. В этом образце конечные точки не указаны, и поэтому предоставляется доступ к конечной точке по умолчанию.  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2.  Откройте узел службы, загрузите веб-канал из службы, отобразите веб-канал и дождитесь нажатия клавиши ВВОД пользователем.  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>Вызов GetBlog с помощью HTTP GET  
  
1.  Откройте Internet Explorer, введите следующий URL-адрес и нажмите клавишу ВВОД: `http://localhost:8000/BlogService/GetBlog`.
  
     URL-адрес содержит базовый адрес службы (`http://localhost:8000/BlogService`), относительный адрес конечной точки и вызываемую операцию службы.  
  
### <a name="to-call-getblog-from-code"></a>Вызов GetBlog() из кода  
  
1.  Создайте <xref:System.Xml.XmlReader> с базовым адресом и вызываемым методом.  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2.  Вызовите статический метод <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>, передав ему только что созданный объект <xref:System.Xml.XmlReader>.  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     Это вызывает операцию службы и заполняет новый <xref:System.ServiceModel.Syndication.SyndicationFeed> с помощью модуля форматирования, возвращенного от операции службы.  
  
3.  Откройте объект веб-канала.  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a>Пример  
 Ниже приведен полный код этого примера.  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 При компиляции приведенного выше кода задайте ссылки на файлы System.ServiceModel.dll и System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>
