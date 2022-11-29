# Needed due to
# http://stackoverflow.com/questions/33395675/cocoapods-file-reference-is-a-member-of-multiple-groups
workspace 'iosMath.xcworkspace'

install! 'cocoapods', :deterministic_uuids => false

target 'iosMathExample' do
  project 'iosMath.xcodeproj'
  pod 'iosMath', :path => './'
end

target 'iosMathTests' do
  project 'iosMath.xcodeproj'
  pod 'iosMath', :path => './'
end

target 'MacOSMath' do
  project 'MacOSMath.xcodeproj'
  pod 'iosMath', :path => './'
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    if target.respond_to?(:product_type) and target.product_type == "com.apple.product-type.bundle"
      target.build_configurations.each do |config|
        config.build_settings['CODE_SIGNING_ALLOWED'] = 'NO'
      end
    end
  end
end
