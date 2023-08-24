# Confusion Matrix
* Overall accuracy can sometimes be a deceptive measure because of unbalanced classes.
* A general improvement to using overall accuracy is to study sensivity and specificity separately
* A confusion matrix represents the prediction summary in matrix form. It shows how many prediction are correct and incorrect per class. It helps in understanding the classes that are being confused by model as other class.
![Matriz de Confusión Básica](https://geekflare.com/wp-content/uploads/2022/07/basic_cm-edited.jpg)

* Code to make a confusion matrix on r (genderPrediction proyect):
  
  ```r
    #tabulate each combination of prediction and actual value
    table(predicted = y_hat, actual = test_set$sex)
    test_set %>% 
      mutate(y_hat = y_hat) %>%
      group_by(sex) %>% 
      summarize(accuracy = mean(y_hat == sex))
    prev <- mean(y == "Male")
    
    confusionMatrix(data = y_hat, reference = test_set$sex)
  ```
