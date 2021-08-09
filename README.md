# UsefulClasses

**LiveDataTestUtil.kt** - Function for unit testing LiveData (https://medium.com/androiddevelopers/unit-testing-livedata-and-other-common-observability-problems-bb477262eb04)

**Resource.kt** - class that allows to wrap any other object around this class and observe the status (Success, Error, Loading)

**Event.kt** - An event wrapper for data that is exposed via a LiveData that represents an event.

    USAGE:  
    liveDataStatus = LiveData<Event<Resource<Class>>> (in ViewModel)
    val value = viewModel.liveDataStatus.getOrAwaitValue() (in Test)
    AssertThat(value.getContentIfNotHandled()?.status).isEqualTo(Status.Error) (in Test)
    
**HiltExt.kt** - It is not possible to use launchFragmentInContainer from the androidx.fragment:fragment-testing library with Hilt, because it relies on an activity that is not annotated with @AndroidEntryPoint. Use this class to run Fragment with Hilt for testing
