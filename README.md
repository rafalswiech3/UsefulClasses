# UsefulClasses

LiveDataTestUtil.kt - Function for unit testing LiveData (https://medium.com/androiddevelopers/unit-testing-livedata-and-other-common-observability-problems-bb477262eb04)

Resource.kt - class that allows to wrap any other object around this class and observe the status (Success, Error, Loading)

Event.kt - An event wrapper for data that is exposed via a LiveData that represents an event.
    USAGE:  liveDataStatus = LiveData<Event<Resource<Class>>>
            val value = viewModel.liveDataStatus.getOrAwaitValue()
            AssertThat(value.getContentIfNotHandled()?.status).isEqualTo(Status.Error)
