```html
<md-input-container ng-if="languageSurvey=='en'" class="add-button" ng-class="{'delete-phone':$index+1 !=multipleChoiceModel.length,'md-input-focused':languageSurvey=='en'?(multipleChoiceModel[$index].OptionValue !=null):(multipleChoiceModel[$index].OptionValueFrench !=null)}" ng-repeat="options in multipleChoiceModel track by $index">
	<label for="MultipleOptions{{$index}}" ng-bind-html="'Surveys.ADD_MULTIPLE'|translate|labelTranslate"></label>
	<input input-focus id="MultipleOptions{{$index}}" ng-required="CheckEmptyArray(multipleChoiceModel)" ng-init="multipleChoiceModel[$index].OptionOrder=$index" opia-validate="'required-error-multiselect'" name="MultipleOptions{{$index}}" class="onfocus animate-if" ng-model="multipleChoiceModel[$index].OptionValue">
	<a href="javascript:;" class="add-icon" ng-if="$index+1 !=multipleChoiceModel.length" ng-click="RemoveMultipleAddedOption($index)"></a>
	<a href="javascript:;" class="add-icon" ng-if="$index+1==multipleChoiceModel.length" ng-click="AddMultipleOption()"></a>
</md-input-container>
```

[[multipleChoiceModel]]
[[AddMultipleOption()]]