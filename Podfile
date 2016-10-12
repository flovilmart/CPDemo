# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'
# 
#

plugin 'cocoapods-mix-frameworks'

target 'CPDemo' do
  pod 'AFNetworking', '~> 2.2'
end

target 'CPDemoFWRK' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!
  pod 'ParseLiveQuery', git: 'https://github.com/parseplatform/ParseLiveQuery-iOS-OSX'
end

def set_build_settings(&f)
    post_install do |installer|
        installer.pods_project.targets.each do |target|
            target.build_configurations.each do |config|
                f.call(config)
            end
        end
    end
end

set_build_settings do |config|
    # Force Swift version
    config.build_settings['SWIFT_VERSION'] = '3.0'
    # Disable code signing
    config.build_settings['CODE_SIGN_IDENTITY[sdk=iphoneos*]'] = ''
end



