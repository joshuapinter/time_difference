[![Build Status](https://travis-ci.org/tmlee/time_difference.png)](https://travis-ci.org/tmlee/time_difference)

# TimeDifference

TimeDifference is the missing Ruby method to calculate difference between two given time. You can do a Ruby time difference in year, month, week, day, hour, minute, and seconds.

## Installation

Add this line to your application's Gemfile:

    gem 'time_difference'

And then execute:

    $ bundle

## Usage

### Get the time difference in year

	# Works for Time, DateTime, and Date
	start_time = Time.new(2013,1)
	end_time = Time.new(2014,1)
	TimeDifference.between(start_time, end_time).in_years
	=> 1.0

	start_time = DateTime.new(2013,1)
	end_time = DateTime.new(2014,1)
	TimeDifference.between(start_time, end_time).in_years
	=> 1.0

	start_time = Date.new(2013,1)
	end_time = Date.new(2014,1)
	TimeDifference.between(start_time, end_time).in_years
	=> 1.0

### Get the time difference in months

	start_time = Time.new(2013,1)
	end_time = Time.new(2014,1)
	TimeDifference.between(start_time, end_time).in_months
	=> 12.0

### Get the time difference in each component

	start_time = Time.new(2013,1)
	end_time = Time.new(2014,1)
	TimeDifference.between(start_time, end_time).in_each_component
	=> {:years=>1.0, :months=>12.0, :weeks=>52.14, :days=>365.0, :hours=>8760.0, :minutes=>525600.0, :seconds=>31536000.0}

### If you would like an overall estimated time component, use in_general (not that accurate)

	start_time = Time.new(2013,1)
	end_time = Time.new(2014,1)
	TimeDifference.between(start_time, end_time).in_general
	=> {:years=>0, :months=>12, :weeks=>0, :days=>5, :hours=>0, :minutes=>0, :seconds=>0}

### Supported time difference includes

	in_years
	in_months
	in_weeks
	in_days
	in_hours
	in_minutes
	in_seconds
	

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
