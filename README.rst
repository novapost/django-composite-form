Usage::

  class ProfileAddressForm(forms.Form):
      address = forms.CharField()
   
   
  class ProfileBirthDayForm(forms.Form):
      birthday = forms.DateField()
   
   
  class ProfileForm(CompositeForm):
      form_list = [ProfileAddressForm, ProfileBirthDayForm]
   
   
  profile_form = ProfileForm({"address": "13 Test St"})
  assert profile_form.errors == {'birthday': [u'This field is required.']}
