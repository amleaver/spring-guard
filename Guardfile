guard :shell do
  watch /.*/ do |m|
    test_file = /\/test\//.match(m[0])
    ruby_file = m[0].reverse[0...3].reverse == '.rb'

    if !test_file && ruby_file
      `pkill -f spring`
      m[0] + ' has changed, restarting spring'
    elsif ENV['SPRING_GUARD_DEBUG']
      m[0] + ' has changed, doing nothing'
    end
  end
end
