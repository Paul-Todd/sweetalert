<p align="center">
    <a href="https://pub.dartlang.org/packages/sweetalert">
        <img src="https://img.shields.io/pub/v/sweetalert.svg" alt="pub package" />
    </a>
 </p>

# sweetalert

sweetalert for flutter.

## Showcases

![](images/preview.gif)

## Getting started

### Add dependency

```
sweetalert: any
```

### Usage


#### Basic usage
![](images/1.png)

```
 SweetAlert.show(context, title: "Just show a message");
```

#### With a subtitle

![](images/2.png)

```
 SweetAlert.show(context,
                      title: "Just show a message",
                      subtitle: "Sweet alert is pretty");
```

#### With a success state

![](images/3.png)

```
 SweetAlert.show(context,
                      title: "Just show a message",
                      subtitle: "Sweet alert is pretty",
                      style: SweetAlertStyle.success);
```

#### With a confirm state

![](images/4.png)


```
SweetAlert.show(context,
                      title: "Just show a message",
                      subtitle: "Sweet alert is pretty",
                      style: SweetAlertStyle.confirm,
                      showCancelButton: true, onPress: (bool isConfirm) {
        if (isConfirm) {
          SweetAlert.show(context,style: SweetAlertStyle.success,title: "Success");
          // return false to keep dialog
          return false;
        }
      });
```

#### Do some job

```
 SweetAlert.show(context,
          subtitle: "Do you want to delete this message",
          style: SweetAlertStyle.confirm,
          showCancelButton: true, onPress: (bool isConfirm) {
        if(isConfirm){
          SweetAlert.show(context,subtitle: "Deleting...", style: SweetAlertStyle.loading);
          new Future.delayed(new Duration(seconds: 2),(){
            SweetAlert.show(context,subtitle: "Success!", style: SweetAlertStyle.success);
          });
        }else{
          SweetAlert.show(context,subtitle: "Canceled!", style: SweetAlertStyle.error);
        }
        // return false to keep dialog
        return false;
      });
```

#### With Widgets for Buttons

![](images/6.png)


```
    SweetAlert.show(context,
      subtitle: "Do you want to delete this message",
      style: SweetAlertStyle.confirm,
      confirmButton: new RaisedButton(
        onPressed: () {
          SweetAlert.show(context,subtitle: "Success!", style: SweetAlertStyle.success);
        },
        color: Colors.purple,
        textColor: Colors.white,
        child: new Text("Confirm"),
      ),
      cancelButton: new RaisedButton(
        onPressed: () {
          SweetAlert.show(context, subtitle: "Cancelled!", style: SweetAlertStyle.error);
        },
        color: Theme.of(context).errorColor,
        child: new Text("Cancel"),
      ),
    );
```

