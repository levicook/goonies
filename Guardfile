# vi: set ft=ruby :

guard 'shell' do

	# anytime a *.go file changes ...
  watch(%r{.*\.go$}) do |match|

		# announce we're going to build
		system('echo `date "+%H:%M:%S"` - building')

		if system('go build') # build

			# announce build passed and we're going to test
			system('echo `date "+%H:%M:%S"` - build OK - testing')

			if system('go test ./...') # test

				# announce test passed and we're going to vet
				system('echo `date "+%H:%M:%S"` - test OK - vetting')

				if system('go vet ./...') # vet

					# announce vet passed
					system('echo `date "+%H:%M:%S"` - vet OK')
				end
			end
		end
	end
end
