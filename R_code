# Loading necessary libraries
library(pROC)

# Reading the dataset
df <- read.csv(file.choose())

# Checking the dataset
head(df)
summary(df)

# Fitting logistic regression model
model <- glm(Outcome ~ ., data = df, family = binomial)

# Summary of the model
summary(model)

# Using step to find the optimal model
optimal_model <- step(model)

# Summary of the optimal model
summary(optimal_model)

# Comparing the two models 
anova(model, optimal_model) 
BIC(model, optimal_model) 
AIC(model, optimal_model) 

# Predictions on the test set 
predicted_values <- predict(optimal_model, newdata = df, type = "response") 
predicted_class <- ifelse(predicted_values > 0.5, 1, 0) 

# Actual values 
actual_values <- df$Outcome 
# Confusion matrix 
conf_matrix <- table(Predicted = predicted_class, Actual = actual_values) 

conf_matrix 

# Extract elements from the confusion matrix
tp <- conf_matrix[2, 2] # True positives
fp <- conf_matrix[2, 1] # False positives
fn <- conf_matrix[1, 2] # False negatives
tp
fp
fn

# Calculate precision and recall
precision <- tp / (tp + fp)
recall <- tp / (tp + fn)
# Calculate F1 score
f1_score <- 2 * (precision * recall) / (precision + recall)
# Calculate accuracy
accuracy <- sum(diag(conf_matrix)) / sum(conf_matrix)
# Print results
print(precision)
print(recall)
print(accuracy)
print(f1_score)

# Plotting the ROC curve 

probab <- predict(optimal_model, newdata = df, type = "response") 
df$prob <- probab 
g1 <- roc(Outcome ~ prob, data = df) 
plot(g1) # Area under the curve 
auc_value <- auc(g1) # AUC measures the model's ability to discriminate between positive and negative classes
auc_value
print("AUC:", auc_value)
